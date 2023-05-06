---
layout: single
title: "Exception"
categories: Java
author_profile: true
toc: true
author_profile: false
---

# Exception

- Exception : 코드 수정에 따라 처리할 수 있는 문제점, 예외
- Error : 코드와 무관하게 원인을 알수 없는 문제점, 에러, 오류
- 자바에서는 예외도 클래스로 규정하여, 예외 객체가 발생하고, 이를 처리해야 한다


```Java
Scanner sc = new Scanner(System.in);
int num;
String input;

System.out.print("정수를 입력 : ");
input = sc.nextLine();
boolean isDigit = true;
for(int i = 0; i < input.length(); i++) {
	if(input.charAt(i) < '0' || '9' < input.charAt(i)) {
		isDigit = false;
	}
}

if(input.contains(".")) {
	System.out.println(".을 포함하면 안됩니다");
}
else if(isDigit == false) {
System.out.println("문자열이 아닌 정수만 입력해야 합니다");
}
else {
	num = Integer.parseInt(input);
	System.out.println("num : " + num);
}
sc.close();
```

    정수를 입력 : .2023
    .을 포함하면 안됩니다
    

정수를 입력 : 가나다라<br>
문자열이 아닌 정수만 입력해야 합니다
<br><br>
정수를 입력 : 2023<br>
num : 2023

### Try-catch

- Try-catch문은 예외를 처리하기 위한 구문이다
- try 문에서 Exception 예외가 발생할 경우 catch (Exception e) 로 빠져서 그 안의 실행문을 실행한다.
- finally는 try-catch문과 함께 예외발생 여부과 관계없이 "항상. 무조건" 실행되어야할 코드를 적는다.
- finally은 필수는 아니며 마지막에 선택적으로 덧붙여 사용한다.


```Java
try {

//예외발생할 가능성이 있는 문장 
    
}
catch(Exception1 e1) {

 //Exception1이 발생했을 경우, 이를 처리하지 위한 문장적는다.
 //보통 이곳에 예외메세지를 출력하고 로그로 남김.
 
}catch(Exception2 e2) {

 //Exception2이 발생했을 경우, 이를 처리하지 위한 문장적는다.
 
}catch(ExceptionN eN) {

 //ExceptionN이 발생했을 경우, 이를 처리하지 위한 문장적는다.
 
}finally{

//예외발생여부에 관계없이 상항 수행되어야 하는 문장적는다.

}
```
