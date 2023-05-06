---
layout: single
title: "HTML_Basic(1)"
categories: HTML
author_profile: true
toc: true
author_profile: false
---

# HTML 기본 문법 (1)

### HTML 이란

<b>HTML(Hyper Text Markup Language)은 가장 단순한 형태의 웹 언어이다.<br>
웹 서버에 HTML 문서를 저장하고 있다가 클라이언트가 특정 HTML 페이지를 요청하면 <br>
해당 HTML 문서를 클라이언트로 전송한다. 그러면 클라이언트는 이 웹 페이지를 해석하여 <br>
웹 브라우저에 표현해 주는데 이런 웹 페이지를 정적인(Static) 웹 페이지라고 한다.<br></b>

### h태그

HTML 주석<br>
주요 제목을 작성하는 태그 h1 ~ h6<br>
h1은 가장 중요한 제목을 작성하는 태그이므로<br>
문서에서 한번만 사용하도록 한다 (페이지 검색과 연관이 있음)<br><br>

vscode에서 alt + shift + ↓ 는 현재 커서 줄을 아래로 복사한다<br>
vscode에서 ctrl + alt + ↓ 는 커서를 수직으로 복사하여 여러줄을 처리하게 한다<br>

<태그 속성="값" 속성="값" ...>내용</태그><br>
- 태그와 속성, 속성과 다른 속성은 띄어쓰기로 구분한다<br>
- 특수한 몇몇 태그를 제외하면, 마무리태그를 반드시 작성해야 한다<br>


<h1 align="left">Headline Level 1</h1>
    <h2 align="center">Headline Level 2</h2>
    <h3 align="right">Headline Level 3</h3>
    <h4>Headline Level 4</h4>
    <h5>Headline Level 5</h5>
    <h6>Headline Level 6</h6>

### Font

<p> paragraph : 문단을 만든다. 문단은 다음 문단과 간격을 둔다 
<br>bold :<b> 글자를 굵게 표시한다</b>
<br> br : break line, 자바의 \n과 같은 역할. 줄바꿈을 수행한다 
 줄바꿈은 문단이 아니므로 다음 줄과의 간격을 두지 않는다 
 br태그는 마무리 태그를 작성하지 않는다 (범위 개념이 없음) 

italic :<i> 글자를 기울임꼴로 표시한다</i>
<br>
underline : <u> 글자에 밑줄을 표시한다</u>
<br>
super : <sup> 글자를 위첨자 처리한다</sup>
<br>
2<sup>10</sup> = 1024<br>
sub : <sub>글자를 아래첨자 처리한다</sub>
<br>
H<sub>2</sub>O
<br>
</p>

### Button


```Java
/* 
<p>
    <h3>button</h3>
    <button>버튼1</button>
    <button>버튼2</button>
    <button>버튼3</button>
    <button>
        <img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fshop1.phinf.naver.net%2F20230217_172%2F16765733228180aYJ2_JPEG%2F77709157649272073_620265343.jpg&type=a340" width="70">
    </button>
</p>
*/
```

<p>
    <h3>button</h3>
    <button>버튼1</button>
    <button>버튼2</button>
    <button>버튼3</button>
    <button>
        <img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fshop1.phinf.naver.net%2F20230217_172%2F16765733228180aYJ2_JPEG%2F77709157649272073_620265343.jpg&type=a340" width="70">
    </button>
</p>

### 펼쳐보기


```Java
/*
<p>
    <h3>details</h3>
    <details>
        <summary>내용 펼치기/접기</summary>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Minima, enim natus. <br>
        Excepturi voluptate aliquid praesentium dolore delectus perspiciatis repellat<br>
         minima odio sunt dicta eveniet inventore asperiores, quisquam commodi? Delectus, repellendus!<br>
    </details>
</p>
*/
```

<p>
    <h3>details</h3>
    <details>
        <summary>내용 펼치기/접기 <<- 클릭 </summary>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Minima, enim natus. <br>
        Excepturi voluptate aliquid praesentium dolore delectus perspiciatis repellat<br>
         minima odio sunt dicta eveniet inventore asperiores, quisquam commodi? Delectus, repellendus!<br>
    </details>
</p>

### List


```Java
/*
<p>
    <h3>unordered list</h3>
    <ul>
        <li>spring framework</li>
        <li>node.JS</li>
        <li>PHP</li>
        <li>Python Django</li>
        <li>.NET C#</li>
    </ul>
</p>
*/
```

<p>
    <h3>unordered list</h3>
    <ul>
        <li>spring framework</li>
        <li>node.JS</li>
        <li>PHP</li>
        <li>Python Django</li>
        <li>.NET C#</li>
    </ul>
</p>


```Java
/*
<p>
    <h3>ordered list</h3>
    <ol>
        <li>Java</li>
        <li>DB</li>
        <li>HTML/CSS</li>
        <li>JSP</li>
        <li>Spring</li>
        <li>Javascript</li>
        <li>API</li>
    </ol>
</p>
*/
```

 <p>
    <h3>ordered list</h3>
    <ol>
        <li>Java</li>
        <li>DB</li>
        <li>HTML/CSS</li>
        <li>JSP</li>
        <li>Spring</li>
        <li>Javascript</li>
        <li>API</li>
    </ol>
</p>

### 테이블

 <blockquote>
    표를 그리기 위해 사용한다<br>
    줄과 칸으로 구성하며, 태그 포함관계를 이해하고 있어야 한다
</blockquote>
 
 <ul>
    <li><b>table</b> : 표 전체의 영역을 나타낸다</li>
    <li><b>tr</b> : table row, 표 안에서의 한 줄을 나타낸다</li>
    <li><b>td</b> : table data, 줄 안에서의 한 칸을 나타낸다</li>
    <li><b>th</b> : table headline, td와 같으나 가운데 정렬 및 굵게가 적용된다</li>
    <li><b>thead</b> : 표의 상단부를 나타낸다. 생략 가능</li>
    <li><b>tbody</b> : 표의 본문을 나타낸다. 생략 가능</li>
    <li><b>tfoot</b> : 표의 하단을 나타낸다. 생략 가능</li>
</ul>


```Java
/*
<table border="2" cellpadding="10" cellspacing="0">
    <tr>
        <th colspan="3">샘플 테이블 (1)</th>
        <td rowspan="4">😃</td>
    </tr>
    <tr>
        <th>이름</th>
        <th>나이</th>
        <th><font color="blue">사진</font></th>
    </tr>        
    <tr>
        <td>박명수</td>
        <td>54</td>
        <td><img src="https://search.pstatic.net/common?type=b&size=216&expire=1&refresh=true&quality=100&direct=true&src=http%3A%2F%2Fsstatic.naver.net%2Fpeople%2F123%2F20220407124334911.jpg" height="5"></td>
    </tr>
    <tr>
        <td>유재석</td>
        <td>52</td>
        <td><img src="https://search.pstatic.net/common?type=b&size=216&expire=1&refresh=true&quality=100&direct=true&src=http%3A%2F%2Fsstatic.naver.net%2Fpeople%2Fportrait%2F202305%2F20230504165031977.jpg" height="5" ></td>
    </tr>
</table>
*/
```

<table border="2" cellpadding="10" cellspacing="0">
    <tr>
        <th colspan="3">샘플 테이블 (1)</th>
        <td rowspan="4">😃</td>
    </tr>
    <tr>
        <th>이름</th>
        <th>나이</th>
        <th><font color="blue">사진</font></th>
    </tr>        
    <tr>
        <td>박명수</td>
        <td>54</td>
        <td><img src="https://search.pstatic.net/common?type=b&size=216&expire=1&refresh=true&quality=100&direct=true&src=http%3A%2F%2Fsstatic.naver.net%2Fpeople%2F123%2F20220407124334911.jpg" height="5"></td>
    </tr>
    <tr>
        <td>유재석</td>
        <td>52</td>
        <td><img src="https://search.pstatic.net/common?type=b&size=216&expire=1&refresh=true&quality=100&direct=true&src=http%3A%2F%2Fsstatic.naver.net%2Fpeople%2Fportrait%2F202305%2F20230504165031977.jpg" height="5" ></td>
    </tr>
</table>    
