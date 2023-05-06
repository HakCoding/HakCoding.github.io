---
layout: single
title: "SupurClase_Ex"
categories: Java
author_profile: true
toc: true
author_profile: false
---

# SupurClase_Ex

### 다음 메인함수의 내용이 잘 작동하도록 클래스를 구성하세요

- Cat과 Dog의 공통속성을 묶어서 처리할 슈퍼클래스 Animal을 작성하세요
- 필요하다면, 생성자를 수정하여 상속관계에 맞게 작동하도록 수정하세요
- Human에서는 나누어져있는 give메서드를 하나로 통일하세요

- give메서드에서 Animal타입의 객체를 전달받았을때
- 만약 그 객체가 Cat의 인스턴스라면 츄르를 주게 하고,
- 만약 그 객체가 Dog의 인스턴스라면 육포를 주게 변경하세요
- 만약 그 객체가 Cat과 Dog가 아니라면 치즈를 주세요
- Human을 상속받는 클래스 Friend 를 작성하세요
- Animal을 전달받는 give와 Human을 전달받는 give로 오버로딩하세요


```Java
public class Human {
	String name;
	
	Human(String name) {
		this.name = name;
	}
	
	void give(Animal ob) {
		String feed = "먹이";
		if(ob instanceof Cat) {
			feed = "츄르";
		}
		else if(ob instanceof Dog) {
			feed = "육포";
		}
		System.out.printf("%s가 %s에게 %s를 준다\n", name, ob.name, feed);
	}
	
	void give(Human ob) {
		String feed = "치즈";
		System.out.printf("%s가 %s에게 %s를 준다\n", name, ob.name, feed);
	}
}	

public class Animal {
	String name;
	
	Animal(String name) {
		this.name = name;
	}
}

public class Cat extends Animal {
	
	Cat(String name) {
		super(name);
	}
}

public class Dog extends Animal {
	
	Dog(String name) {
		super(name);
	}
}

public class Friend extends Human {
	Friend(String name) {
		super(name);
	}
}

Human man = new Human("철수");
	Cat cat = new Cat("나옹이");
	Dog dog = new Dog("바둑이");
	Friend f = new Friend("영희");
	
	man.give(cat);	
	man.give(dog);	
	man.give(f); 	
```

    철수가 나옹이에게 츄르를 준다
    철수가 바둑이에게 육포를 준다
    철수가 영희에게 치즈를 준다
    
