# 연산자

연산자 : 프로그래밍 언어에서 값을 계산/처리 하기 위해 사용하는 기호 혹은 단어

- 산술연산자 : +, -, *, /, %
- 정수간의 연산은 결과가 정수로 나타난다 (3 + 2 = 5)
- 실수가 포함되면 결과는 실수로 나타난다 (3 + 2.2 = 5.2)
- add, sub, mul, div
- 숫자끼리 더하면 덧셈을 수행하고, 문자열이 포함되면 이어붙이기(append)를 수행한다
- \+ 연산자는 오버로딩 되어있다(하나의 기호가 상황에 따라 다른 작동을 할 수 있다)
- \- 연산자는 문자열에 대하여 작동하지 않는다
- 자바의 문자열에는 substring 이라는 함수가 있으며 문자열 빼기의 기능을 담당한다
- \* 연산자는 문자열에 대해서 작동하지 않는다 (숫자에 대해서만 사용한다)
- 자바는 포인터를 사용하지 않으니까, * 기호는 포인터 연산이 아니다
- / 연산자는 타입에 따라 몫만 구할 수도 있고, 소수점까지 계산할 수도 있다

## 예제 JAVA 코드


```Java
int a = 10;
		int b = 20;
		int c = 31;
		int total = a + b + c;
		int count = 3;
		double avg1 = total / 3;
		double avg2 = total / 3.0;
		double avg3 = total / (double)count;	// 강제형변환(casting)
		System.out.println("avg1 : " + avg1);	// syso, ctrl + space
		System.out.println("avg2 : " + avg2);
		System.out.println("avg3 : " + avg3);
```

    avg1 : 20.0
    avg2 : 20.333333333333332
    avg3 : 20.333333333333332
    

		
### 1) 정수에서 짝수, 홀수, 약수, 배수 등을 확인할 때 사용한다
  - % 연산자는 정수형태로 나머지를 구한다


```Java
int n1 = 10;
		int n2 = 3;
		System.out.println(n1 % n2);
		System.out.println(10 % 2);	// 2로 나누어 떨어지면 짝수
		System.out.println(11 % 2);	// 2로 나누어 떨어지지 않으면 홀수
```

    1
    0
    1
    

### 2) 정수의 자릿수를 구분할 때 사용한다
 - 10의 n승으로 구성된 숫자로 나누면, 0의 개수만큼 뒷자리를 떼어낼 수 있다


```Java
int birth = 1208;
		int day = birth % 100;	
		int month = birth / 100;
		System.out.printf("생일은 %d월 %d일입니다\n", month, day);
        System.out.println();
```

    생일은 12월 8일입니다
    
    

### 3) 난수(랜덤)의 범위를 제한할 수 있다


```Java
Random ran = new Random();
	int num = ran.nextInt();
	num = num < 0 ? -num : num;  // 0보다 작으면 부호를 반전시켜서 저장한다
	System.out.println("첫번째로 뽑은 난수 : " + num);
	
	int num2 = num % 6;
	System.out.println("6으로 나눈 나머지 : " + num2);
	
	int num3 = num2 + 1;
	System.out.println("1을 더한 결과 : " + num3);
```

    첫번째로 뽑은 난수 : 1847749748
    6으로 나눈 나머지 : 2
    1을 더한 결과 : 3
    

- 대입연산자 : =, +=, -=, *=, /=, %=
- a = b
- a변수에 b변수가 가지고 있는 현재 값을 복사하여 저장한다
- 우변의 값을 좌변의 공간에 복사하여 저장한다
- 우변에 연산식이 있다면, 연산이 끝난 후의 값을 저장한다
- 우변에 함수가 있다면, 함수를 실행한 결과가 나온 이후 저장한다
- 항상 오른쪽을 먼저 처리하며, 오른쪽에 결과가 정해지면 왼쪽에 담는다


```Java
int t1 = 10;		// 상수를 저장한다
		int t2 = t1;		// 변수의 값을 저장한다
		int t3 = t2 + 5;	// 연산식의 결과를 저장한다
		int t4 = ran.nextInt();	// 함수실행결과를 저장한다
		
		System.out.println("t1 = " + t1);
		System.out.println("t2 = " + t2);
		System.out.println("t3 = " + t3);
		System.out.println("t4 = " + t4);
```

    t1 = 10
    t2 = 10
    t3 = 15
    t4 = 1610620546
    

### 비교 연산자

- 비교 연산자 : >, <, >=, <=, ==, !=
- 비교 연산의 결과는 boolean 형태로 나타난다 (true / false)


```Java
System.out.println("n1 > n2 : " + (n1 > n2));	// 초과 (gt)
	System.out.println("n1 < n2 : " + (n1 < n2));	// 미만
	System.out.println("n1 >= n2 : " + (n1 >= n2));	// 이상
	System.out.println("n1 <= n2 : " + (n1 <= n2));	// 이하
	System.out.println("n1 == n2 : " + (n1 == n2));	// 일치
	System.out.println("n1 != n2 : " + (n1 != n2));	// 불일치
```

    n1 > n2 : true
    n1 < n2 : false
    n1 >= n2 : true
    n1 <= n2 : false
    n1 == n2 : false
    n1 != n2 : true
    

- if, while, for, 삼항연산 등에 활용되기 때문에 중요도가 높다


```Java
int age = 25;
	boolean isAdult = age >= 20;
	System.out.println("성인 여부 : " + isAdult);
```

    성인 여부 : true
    
