---
layout: single
title: "Function"
categories: Java
author_profile: true
toc: true
author_profile: false
---

# 함수

- 일정한 코드를 특정 이름으로 묶어둔 내용
- 일정한 코드에 의해서 값을 계산하는 내용
- 변수, 상수 와 마찬가지로 어떤 값을 만들어내는 개체, 함수
- void 형태의 함수는 값을 만들어내지 않는다
- 자바에서 코드의 기본 단위는 Class 이다
- 따라서, 모든 함수는 클래스 내부에 만들어진다
- main 함수에서 호출(실행)하고 싶은 함수는 반드시 static을 붙여서 작성해야 한다

### 함수 만들기

- main 밖에 두값을 더하는 함수를 만들어준다


```Java
static int add(int n1, int n2) {
    int answer = n1 + n2;
    return answer;
}
```

main 안으로 함수를 호출하면 입력값이 계산이 된다


```Java
int t1 = add(10, 20);
System.out.println("t1 : " + t1);
```

    t1 : 30
    

### 함수 만들기 예시

- 제곱값을 구하는 함수


```Java
static int pow(int n1, int n2) {
int answer = 1;
for(int i = 0; i < n2; i++) {
	answer *= n1;
}
return answer;
}
```

- 2의 10 제곱 값


```Java
int t2 = pow(2, 10);
System.out.println("t2 : " + t2);
```

    t2 : 1024
    

### 두 숫자중 큰숫자 찾는 함수


```Java
static int bigNumber(int n1, int n2) {
    int answer = n1;
    if(answer < n2) {
        answer = n2;
    }
    return answer;
}
```

- 12와 23을 비교하여 큰숫자를 출력


```Java
int t3 = bigNumber(12, 23);
System.out.println("t3 : " + t3);
```

    t3 : 23
    
