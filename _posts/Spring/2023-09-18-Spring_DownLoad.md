---
layout: single
title: "Sping 다운로드"
categories: DownLoad
author_profile: true
toc: true
author_profile: false
---

<h1>스프링 다운로드</h1>

<h3>1) 이클립스 다운로드</h3>

<img src="https://hakcoding.github.io/img/스프링 이클립스.png" width="500" height="500" align="left">

이클립스 다운로드 : https://www.eclipse.org/downloads/ (필요한 버전 다운로드)

<h3>2) 이클립스 압축 풀기</h3>

1) 원하는 위치에 압축을 푼다
2) 개발 환경에 필요한workspace 폴더를 생성

<h3>3) Tomcat 설치</h3>

<img src="https://hakcoding.github.io/img/톰캣다운로드.png" width="500" height="500" align="left">

톰캣 다운로드 : https://tomcat.apache.org/download-80.cgi
(필요한 버전 다운로드)

<h3> 4) 톰캣 압축 풀기</h3>

1. 원하는 위치에 압축을 푼다.
2. 윈도우키 + R 을 눌러 실행창을 열어 sysdm.cpl을 입력 한다
3. 시스템 속성의 고급 탭에서 환경변수를 클릭 한다
4. 새로 만들기를 클릭하여 JAVA_HOME 을 등록 (만약 되어있으면 생략)

<h3> 5) 환경 변수 확인</h3>

1. 윈도우 + R 을 눌러 실행창을 켠후 cmd를 입력
2. catalina start를 입력
3. Tomcat이 실행된다면 환경변수가 등록이 되었다는 뜻

<img src="https://hakcoding.github.io/img/톰캣확인.png" width="800" height="300" align="left">

<h3> 6) 이클립스 설정</h3>

1. 이클립스 실행
2. Windows > Preferences 클릭

<img src="https://hakcoding.github.io/img/이클립스 설정1.png" width="500" height="500" align="left">

3. General > Workspace > Text file encoding > UTF-8로 변경

<img src="https://hakcoding.github.io/img/이클립스 설정 2.png" width="500" height="500" align="left">

4. Web > CSS Files / HTML Files / JSP Files > UTF-8로 변경

<img src="https://hakcoding.github.io/img/이클립스 설정 3.png" width="500" height="500" align="left">

5. General > Web Browser > Use external web browser 선택 (본인의 ppt 설정)

<img src="https://hakcoding.github.io/img/이클립스 설정 4.png" width="500" height="500" align="left">

6. Server > Add... > 자신의 톰캣 버전 클릭 > JRE 에는 설치된 자바가 하나면 default를 설치된 자바가 여러개면 1.8 버전을 선택해 Finish를 클릭

<img src="https://hakcoding.github.io/img/이클립스 설정 5.png" width="700" height="700" align="left">

7. Help > Eclipse Marketplace…  (eclipse에서 Spring framework를 사용하기 위한 준비)

<img src="https://hakcoding.github.io/img/이클립스 설정 6.png" width="700" height="700" align="left">

8. Find 에 str 검색 (Spring Tools 아이콘이 나타나지 않을경우 풀네임으로 검색)

<img src="https://hakcoding.github.io/img/이클립스 설정 7.png" width="500" height="500" align="left">

9. 전체 체크 후 Confirm 클릭

<img src="https://hakcoding.github.io/img/이클립스 설정 8.png" width="500" height="500" align="left">

10. 우측하단 100% 되는거 확인

<img src="https://hakcoding.github.io/img/이클립스 설정 9.png" width="500" height="500" align="left">

11. 설치중 Warning 메세지가 뜬다면 Install anyway를 선택하고 체크박스를 선택한 후 Accept selected

<img src="https://hakcoding.github.io/img/이클립스 설정 10.png" width="500" height="500" align="left">

12. 설치가 완료 되면 Restart Now를 선택해 Eclipse를 재시작

<img src="https://hakcoding.github.io/img/이클립스 설정 11.png" width="500" height="500" align="left">
