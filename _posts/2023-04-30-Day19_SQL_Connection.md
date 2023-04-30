---
layout: single
title: "SQL_Connection"
categories: Java
author_profile: true
toc: true
author_profile: false
---

# SQL 연동


```Java
String driverName = OracleDriver.class.getName();
Connection conn = null;
Statement stmt = null;
ResultSet rs = null;

String user = "c##itbank";
String password = "it";
String url = "jdbc:oracle:thin:@192.168.1.100:1521:xe";

try {
String sql = "select banner from v$version";
Class.forName(driverName);
conn = DriverManager.getConnection(url, user, password);
stmt = conn.createStatement();
rs = stmt.executeQuery(sql);

while(rs.next()) {
String data = rs.getString("banner");
	System.out.println(data);
	}
	
} catch(ClassNotFoundException e) {
	System.out.println("클래스 이름이 잘못되었습니다");
	
} catch(SQLException e) {
	e.printStackTrace();
	
} finally {
	try { if(rs != null)   rs.close();   } catch(Exception e) {}
	try { if(stmt != null) stmt.close(); } catch(Exception e) {}
	try { if(conn != null) conn.close(); } catch(Exception e) {}
}
```
