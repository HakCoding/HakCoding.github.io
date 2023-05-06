---
layout: single
title: "Object_Class"
categories: Java
author_profile: true
toc: true
author_profile: false
---

# Object_Class

- Object 클래스는 자바의 모든 클래스의 최상위 슈퍼 클래스이다
- 자바의 모든 객체는 Object클래스의 특성을 상속받게 되어 있다
- 다중 상속은 불가능하므로, 슈퍼클래스가 있다면 Object를 상속받지 않으나
- 그 슈퍼클래스가 Object를 상속받게 된다

### object 확인


```Java
class A /* extends Object */ {
	
}
class B extends A {
	
}
```


```Java
B ob = new B();
System.out.println(ob.getClass());
	System.out.println(ob.getClass().getSimpleName());
	System.out.println(ob.toString());
	System.out.println(ob.equals(null));
```

class object.B <br>
B <br>
object.B@73a28541 <br>
false <br>

### 어떤 객체의 슈퍼클래스를 찾아올라가는 방법


```Java
Scanner sc = new Scanner(System.in);
	
String scannerClassName = sc.getClass().getName();
String superName = sc.getClass().getSuperclass().getName();

System.out.println("scanner : " + scannerClassName);
System.out.println("scanner의 슈퍼클래스 이름 : " + superName);

sc.close();
```

    scanner : java.util.Scanner
    scanner의 슈퍼클래스 이름 : java.lang.Object
    

### 다른 클래스의 슈퍼클래스 정보를 찾아보자


```Java
Integer num = new Integer(150);
System.out.println();
System.out.println("Integer");
System.out.println(num.getClass().getName());

System.out.println("Integer의 슈퍼클래스는 " + num.getClass().getSuperclass().getName());

System.out.println("Integer의 슈퍼의 슈퍼클래스는 " + Integer.class.getSuperclass().getSuperclass().getName());
```

    
    Integer
    java.lang.Integer
    Integer의 슈퍼클래스는 java.lang.Number
    Integer의 슈퍼의 슈퍼클래스는 java.lang.Object
    

### 객체의 상위 클래스 알아보기


```Java
static int getDistanceFromObject(Class clazz) {
	int count = 0;
	while(true) {			
		System.out.println(clazz.getName());
		if(clazz.equals(Object.class)) {
			break;
		}
		clazz = clazz.getSuperclass();
		count++;
	}
	System.out.println();
	return count;
}
    
int t1 = getDistanceFromObject(Scanner.class);
	int t2 = getDistanceFromObject(Integer.class);
	int t3 = getDistanceFromObject(Number.class);
	int t4 = getDistanceFromObject(ArrayList.class);
	
	System.out.println("Scanner는 Object와의 거리가 " + t1);
	System.out.println("Integer는 Object와의 거리가 " + t2);
	System.out.println("Number는 Object와의 거리가 " + t3);
	System.out.println("ArrayList는 Object와의 거리가 " + t4);
```

    java.util.Scanner
    java.lang.Object
    
    java.lang.Integer
    java.lang.Number
    java.lang.Object
    
    java.lang.Number
    java.lang.Object
    
    java.util.ArrayList
    java.util.AbstractList
    java.util.AbstractCollection
    java.lang.Object
    
    Scanner는 Object와의 거리가 1
    Integer는 Object와의 거리가 2
    Number는 Object와의 거리가 1
    ArrayList는 Object와의 거리가 3
    
