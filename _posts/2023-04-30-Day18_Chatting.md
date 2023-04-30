---
layout: single
title: "Chatting"
categories: Java
author_profile: true
toc: true
author_profile: false
---

# 클라이언트 끼리 채팅

### Client


```Java
package multiChat;

import java.io.IOException;
import java.io.PrintWriter;
import java.net.Socket;
import java.util.NoSuchElementException;
import java.util.Scanner;

// 클라이언트 끼리 채팅하는 내용

class Sender implements Runnable {
	
	private Scanner sc;
	private Socket so;
	private PrintWriter pw;
	
	public Sender(Socket so, Scanner sc) {
		try {
			this.so = so;
			this.sc = sc;
			pw = new PrintWriter(so.getOutputStream());
			
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
	
	@Override
	public void run() {
		String msg;
		while(true) {
			System.out.print("메시지 입력 : ");
			msg = sc.nextLine();
			pw.println(msg);
			pw.flush();
			if(msg.equals("exit")) {
				break;
			}
		}
		try { so.close(); } catch (IOException e) {}
	}
}

class Reciever implements Runnable {
	private Scanner server;
	
	public Reciever(Socket so) {
		try {
			server = new Scanner(so.getInputStream());
			
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
	
	@Override
	public void run() {
		String msg;
		//try {
			while(true) {
				msg = server.nextLine();
				System.out.println(msg);
				if(msg == null) {
					break;
				}
			}
//		} catch(NoSuchElementException e) {
//			System.out.println("프로그램 종료");
//		}
	} 	// end of run
}

public class Client {
	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		Socket so;
		String host;
		int port = 7777;
		
		System.out.print("접속할 서버의 IP 입력 : ");
		host = sc.nextLine();
		
		try {
			so = new Socket(host, port);
			// 메세지를 보내거나 받는 요소가 동시에 수행되어야 한다
			
			Sender sender = new Sender(so, sc);
			Reciever reciever = new Reciever(so);
			Thread th1 = new Thread(sender);
			Thread th2 = new Thread(reciever);
			
			th1.start();
			th2.run();
			
		} catch(IOException e) {
			e.printStackTrace();
		}
		
		sc.close();
	}
}

```

### Server


```Java
class Session implements Runnable {

	private PrintWriter pw;
	private Scanner sc;
	private InetAddress inetAddress;
	static ArrayList<Session> list = new ArrayList<>();

	public Session(Socket so) {
		try {
			pw = new PrintWriter(so.getOutputStream());
			sc = new Scanner(so.getInputStream());
			inetAddress = so.getInetAddress();
			list.add(this); // 만들어진 세션 자기 자신을 리스트에 추가한다

		} catch (IOException e) {
			e.printStackTrace();
		}
	}

	Session() {
		this.pw = new PrintWriter(System.out);
		try {
			inetAddress = InetAddress.getLocalHost();
		} catch (UnknownHostException e) {
			e.printStackTrace();
		}
	}

	public PrintWriter getPrintWriter() {
		return pw;
	}

	@Override
	public void run() {
		String msg;
		while (true) {
			msg = sc.nextLine(); // 한명의 클라이언트에게 메시지를 전달받아서
			for (Session session : Session.list) { // 리스트에 저장된 모든 출력요소에 전달한다
				session.getPrintWriter().println(msg);
				session.getPrintWriter().flush();
			}
			if (msg.equals("exit")) {
				break;
			}
		}
		try {
			pw.close();
		} catch (Exception e) {
		}
		list.remove(this); // 접속을 종료하면 pw를 close하고, 자기자신을 리스트에서 제거한다
	}

	@Override
	public String toString() {
		return inetAddress.toString() + " 세션";
	}
}

// 서버는 클라이언트들을 연결해주는 중개역할
public class Server {

	// 서버 컴퓨터의 IP 중에서 가상 IP이거나 루프백 IP를 제외한 실제 IP를 찾아주는 메서드
	private static String getLocalServerIp() {
		try {
			for (Enumeration<NetworkInterface> en = NetworkInterface.getNetworkInterfaces(); en.hasMoreElements();) {
				NetworkInterface intf = en.nextElement();
				for (Enumeration<InetAddress> enumIpAddr = intf.getInetAddresses(); enumIpAddr.hasMoreElements();) {
					InetAddress ia = enumIpAddr.nextElement();
					if (!ia.isLoopbackAddress() && !ia.isLinkLocalAddress() && ia.isSiteLocalAddress()) {
						return ia.getHostAddress();
					}
				}
			}
		} catch (SocketException ex) {
		}
		return null;
	}

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);
		String localIP = getLocalServerIp();
		ServerSocket ss;
		Socket so;
		int port = 7777;
		Session session;

		try {

			ss = new ServerSocket(port); // 서버 개설
			System.out.printf("서버 아이피는 [%s] 입니다\n", localIP);

			// 서버도 채팅내용을 보고 싶다
			Session.list.add(new Session());

			while (true) {
				System.out.println("접속 대기중...");
				so = ss.accept();
				session = new Session(so);
				Thread th = new Thread(session);
				th.start();

				System.out.println("현재 접속 인원 : " + Session.list.size());

				Session.list.forEach(System.out::println);
				System.out.println();
			}

		} catch (IOException e) {
			e.printStackTrace();
		}
		sc.close();

	}
}
```
