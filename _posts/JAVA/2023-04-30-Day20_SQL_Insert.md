---
layout: single
title: "SQL_Insert"
categories: Java
author_profile: true
toc: true
author_profile: false
---


# SQL 데이터 입력



### Main


```Java
ProductSalesDAO dao = new ProductSalesDAO();
Scanner scanner = new Scanner(System.in);
HashMap<String, String> map = new HashMap<String, String>();
int mune;

map.put("상품이름", "매출합계");

while (true) {
	System.out.println("1. 전체상품목록");
	System.out.println("2. 등록상품목록");
	System.out.println("3. 미등록상품목록");
	System.out.println("0. 종료");
	System.out.print("선택 >>");
	
	System.out.print("입력 : ");
	mune = Integer.parseInt(scanner.nextLine());

	if (mune == 1) {
		dao.allResult();
	}
	if (mune == 2) {
		dao.registeredResult();
	}
	if (mune == 3) {
		dao.unregisteredResult();
	}
	if (mune == 0) {
		scanner.close();
		break;
	}
}
```

### DAO


```Java
public class ProductSalesDAO {
	
	Connection conn;
	PreparedStatement pstmt;
	ResultSet rs;
	
	String user = "c##itbank";
	String password = "it";
	String url = "jdbc:oracle:thin:@192.168.1.100:1521:xe";
	
	public ProductSalesDAO() {
		try {
			Class.forName("oracle.jdbc.driver.OracleDriver");
		} catch (Exception e) {
			e.printStackTrace();
			System.out.println("잘못된 클래스 이름 예외");
		}
	}
	public ArrayList<HashMap<String, Object>> allResult() { // 전체 품목별 매출 합계
		ArrayList<HashMap<String, Object>> list = new ArrayList<>();
		String sql = "";
		return list;		
	}
	public ArrayList<HashMap<String, Object>> registeredResult() {		// 등록 상품명 매출 합계
		ArrayList<HashMap<String, Object>> list = new ArrayList<>();
		String sql = "";
		return list;		
	}
	public ArrayList<HashMap<String, Object>> unregisteredResult() {	// 미등록 상품 매출 합계
		ArrayList<HashMap<String, Object>> list = new ArrayList<>();
		String sql = "";
		return list;		
	}
}
```
