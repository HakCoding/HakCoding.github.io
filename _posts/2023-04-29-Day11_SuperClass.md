---
layout: single
title: "SuperClass"
categories: Java
author_profile: true
toc: true
author_profile: false
---

# SuperClass

 1) 서브클래스의 생성자는 슈퍼클래스의 생성자를 반드시 호출해야 한다
 2) 생성자를 직접 작성하지 않으면, 기본생성자를 만들어준다
 3) 매개변수를 받는 생성자를 작성하면 기본생성자가 사라진다
 4) 슈퍼클래스의 생성자 모양에 맞게 서브클래스에서 직접 호출하도록 설정해야 한다


```Java
class Pos2D {				// 슈퍼클래스 (부모클래스, 상위클래스)
	private int x, y;
	
	public Pos2D(int x, int y) {
		this.x = x;
		this.y = y;
	}
	public void show() {
		System.out.println("x : " + x + ", y : " + y);
	}
	public int getX() {
		return x;
	}
	public int getY() {
		return y;
	}
}
class Pos3D extends Pos2D {	// Pos2D의 내용을 상속받아서, 추가속성과 기능을 작성한 새로운 클래스
							// 서브 클래스 (자식클래스, 하위클래스)
	private int z;
	
	public Pos3D(int x, int y, int z) {	// 서브클래스는 슈퍼클래스의 생성자를 반드시 호출해야만 한다
//		this.x = x;
//		this.y = y;
		super(x, y);	// Pos2D(int x, int y)	// 생성자의 첫번째 줄에서 호출
		this.z = z;
	}
	
	@Override			// 물려받은 기능(함수)의 형식은 유지하면서, 내용을 새로 작성한다
	public void show() {
		System.out.printf("x : %d, y : %d, z : %d\n", getX(), getY(), z);
	}
  public int getZ() {
		return z;
	}
}  
    
	Pos2D ob1 = new Pos2D(3, 4);
		ob1.show();
    Pos3D ob2 = new Pos3D(2, 3, 5);
		// Pos3D 호출 -> Pos2D(x, y) -> Pos3D(z) -> 객체 생성 완료
		ob2.show();     
```

    x : 3, y : 4
    x : 2, y : 3, z : 5
    


```Java
class Human {					// 사람
	private String name;
	private int age;
	
	public Human(String name, int age) {
		this.name = name;
		this.age = age;
		// 0) 서브클래스의 생성자는 슈퍼클래스의 생성자를 반드시 호출해야 한다
		// 1) 생성자를 직접 작성하지 않으면, 기본생성자를 만들어준다
		// 2) 매개변수를 받는 생성자를 작성하면 기본생성자가 사라진다
		// 3) 슈퍼클래스의 생성자 모양에 맞게 서브클래스에서 직접 호출하도록 설정해야 한다
	}
	
	public void show() {
		System.out.printf("이름은 %s이고, 나이는 %d살입니다\n", name, age);
	}

	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
}
class Doctor extends Human {	// 의사
	private String major;
	
	public Doctor(String name, int age, String major) {
		super(name, age);
		this.major = major;
	}
	
	public void show() {
		System.out.printf("%s 의사 %s이고, 나이는 %d살입니다\n", major, getName(), getAge());
	}
	
	public void heal(Human target) {
		System.out.println(target.getName() + " 환자를 치료합니다");
	}
}
class Student extends Human {	// 학생
	private int score;

	public Student(String name, int age, int score) {
		super(name, age);
		this.score = score;
	}
	
	public void show() {
		System.out.printf("학생 %s이고, 나이는 %d살, 점수는 %d점입니다\n", getName(), getAge(), score);
	}
}

// 상속관계를 나타내기 위한 두 클래스는 개념적으로 포함관계에 있어야 한다
		// 구조적인 포함관계가 아님을 주의
		// 1) 의사는 사람이다 (O)		의사는 사람 카테고리에 포함된다
		// 2) 타이어는 자동차다 (X)		타이어는 구조적으로 자동차 부품에 포함되나, 그 자체가 자동차는 아니다
		
		// 서브클래스의 객체는 슈퍼클래스의 다른 서브클래스로 대체될 수 있어야 한다
		// 의사는 사람에 해당하는 다른 클래스의 인스턴스로 대체될 수 있어야 한다
		
		// 옆집 의사선생님 -> 옆집 학생
		// 우리집 자동차를 타고 이동한다 -> 우리집 타이어를 타고 이동한다 (?)
		
		// 의사도 사람이고, 학생도 사람이므로, 의사 객체와 학생 객체는 사람 클래스로 처리할 수 있다
		// 서브클래스의 객체를 슈퍼클래스타입으로 형변환 할 수 있다
		// 슈퍼클래스의 변수로 서브클래스의 객체를 저장할 수 있다
		
		// 만약, 각 서브클래스에서 오버라이딩된 메서드가 있다면
		// 타입을 슈퍼클래스로 참조하고 있더라도, 서브클래스의 오버라이딩 메서드가 호출된다
		
		Doctor ob1 = new Doctor("김사부", 42, "흉부외과");
		ob1.show();	// 슈퍼클래스의 메서드를 상속받은 후, 형식을 유지하면서 내용을 재정의한 오버라이딩 메서드
		
		Student ob2 = new Student("해리포터", 24, 100);
		ob2.show();	// 물려받은 내용을 덮어쓴 오버라이딩 메서드
		
		ob1.heal(ob2);
		// 서브클래스 객체는 슈퍼클래스 타입으로 참조할 수 있다
		
		Human ref1 = ob1;	// 의사는 사람이다
		Human ref2 = ob2;	// 학생은 사람이다
		
//		ref1.heal();		// 의사 행세를 하고 있을때만 치료행위를 할 수 있다
		ref1.show(); 		// 사람은 자기소개가 가능하고, 의사가 평소 하던 식 대로 자기소개를 한다
		ref2.show();

```

    흉부외과 의사 김사부이고, 나이는 42살입니다
    학생 해리포터이고, 나이는 24살, 점수는 100점입니다
    해리포터 환자를 치료합니다
    흉부외과 의사 김사부이고, 나이는 42살입니다
    학생 해리포터이고, 나이는 24살, 점수는 100점입니다
    
