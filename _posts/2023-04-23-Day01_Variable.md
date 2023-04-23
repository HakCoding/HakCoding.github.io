---
layout: single
title: "변수"
categories: Class
author_profile: true
toc: true
author_profile: false
---

## Day01_변수

변수 : 프로그램에서 사용할 데이터를 저장하는 메모리공간
변수마다 크기가 다르고 유형도 다르다

1) primitive Type : 데이터를 직접 저장하는 기본 자료형<br>
   byte, boolean, char, short, int, long, float, double<br>
   별도의 형태 정의가 없어도 단순한 형태로 표현할 수 있는 데이터들<br>

   변수 선언 (변수 새로 만들기), 변수 이름은 중복될 수 없다<br>
   자료형 변수이름;<br>
   자료형 변수이름 = 값;<br><br>


```Java
package variable;

public class Ex01_Variable {
	// 이클립스에서 자동완성 : ctrl + space

	public static void main(String[] args) {
boolean bo = true; // 논리값, 1바이트. true 혹은 false만 저장가능

		byte by = 127; 
		short sh = 32767; 
		char ch = 44032; 
		int num = 1234; 
		long ln = 3000000000L; 

		float fl = 1.2F; // 실수, 4바이트
		double db = 3.14; // 실수, 8바이트(기본)<br>
		
System.out.println("bo : " + bo);
		System.out.println("by : " + by);
		System.out.println("sh : " + sh);
		System.out.println("ch : " + ch);
		System.out.println("num : " + num);
		System.out.println("ln : " + ln);
		System.out.println("fl : " + fl);
		System.out.println("db : " + db);
		System.out.println();
```

    bo : true
    by : 127
    sh : 32767
    ch : 가
    num : 1234
    ln : 3000000000
    fl : 1.2
    db : 3.14
    
    

### 변수 크기

<img src="https://t1.daumcdn.net/cfile/tistory/2307CC3F54C4ED2931" width= 500x align="left">
<br><br><br><br><br><br><br><br><br><br><br>
표시형식은 글자이지만, 내부 저장형식은 정수이므로, 덧셈연산이 가능하다 <br>
자바에서 홑따옴표는 단일 글자를 나타내고, 쌍따옴표는 여러글자(문자열)를 나타낸다 <br><br>
2) Reference Type : 다른 곳에 데이터를 생성하고 대상을 참조하는 자료형 <br>
 array, object... <br>
 자신만의 고유한 특정 형식을 가지고 있는 복합적인 데이터들 <br>

 
