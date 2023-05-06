---
layout: single
title: "Selector"
categories: HTML
author_profile: true
toc: true
author_profile: false
---

# 선택자


```Java
/*
<style>
        table {
            border-collapse: collapse;
            border: 2px solid black;
        }
        td, th {
            padding: 5px 10px;
            border: 1px solid grey;
        }
        h3.block {
            background-color: salmon;
            color: white;
            padding: 5px;
            text-align: center;
        }
        tr:nth-child(2n + 1) {  //tr중에서 홀수번째 순번인 요소 
            background-color: lemonchiffon;
        }
        tr:nth-child(2n) {      // tr중에서 짝수번째 순번인 요소 
            background-color: linen;
        }
        tr:first-child {    // 같은 속성을 넣더라도, 적용되는 순서에 따라 결과가 달라진다 
            background-color: salmon;
            color: white;   // 개별 속성은 나중에 작성하는 것이 좋다 
        }
    </style>
</head>
<body>
    <h1>ex01.html - css selector</h1>
    <hr>
    <h3>선택자는 특정 HTML 태그를 선택할 때 사용하는 기능이다</h3>
    <h3 class="block">선택자 { 스타일속성: 스타일값; }</h3>
    <table>
        <tr>
            <th>선택자</th>
            <th>형태</th>
            <th>예시</th>
        </tr>
        <tr>
            <td>전체 선택자</td>
            <td>*</td>
            <td>*</td>
        </tr>
        <tr>
            <td>태그 선택자</td>
            <td>태그</td>
            <td>h1</td>
        </tr>
        <tr>
            <td>아이디 선택자</td>
            <td>#아이디</td>
            <td>#header</td>
        </tr>
        <tr>
            <td>클래스 선택자</td>
            <td>.클래스</td>
            <td>.item</td>
        </tr>
        <tr>
            <td>후손 선택자</td>
            <td>선택자 선택자</td>
            <td>section article</td>
        </tr>
        <tr>
            <td>자손 선택자</td>
            <td>선택자 > 선택자</td>
            <td>ul > li</td>
        </tr>
    </table>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/selecter.png">

### 선택자 종류


```Java
// <style>
//        h3 {    /* 태그 선택자 */
//            text-align: center;
//            color: blue;
//        }
//        #t1 {   /* 아이디 선택자 */
//                /* 아이디는 문서 내부에서 고유한 값이여야 한다 (unique) */
//            color: red;
//        }
//        .item { /* 클래스 선택자 */
//            color: green;
//        }
//    </style>
// </head>
// <body>
//    <h1>ex03.html</h1>
//    <hr>
//
//    <h3 id="t1" class="item">id: t1</h3>
//    <h3 class="item">item1</h3>
//    <h3 class="item">item2</h3>
//    <h3 class="item">item3</h3>
//    <h3>no id, no class, just h3</h3>
//    
// </body>
```

<img src="https://hakcoding.github.io/img/Selector_Type.png">

### 속성 선택자


```Java
/*
<style>
        .desc {
            background-color: salmon;
            color: white;
            padding: 10px;
        }
        input {
            all: unset;
            border-bottom: 2px solid black;
            padding: 5px;
        }
        input[type="text"] {
            background-color: lightcyan;
        }
        input[type="password"] {
            background-color: burlywood;
        }
        input[type="button"][value="확인"] {
            background-color: darkgray;
            border: 1px solid black;
        }
    </style>
</head>
<body>
    <h1>속성 선택자</h1>
    <hr>
    <h3 style="background-color: salmon; 
               color: white; 
               padding: 10px;">
        선택자[속성]
    </h3>
    <h3 class="desc">선택자[속성=값][속성=값]</h3>

    <p>
        <input type="text" name="id" placeholder="아이디">
    </p>
    <p>
        <input type="password" name="pw" placeholder="비밀번호">
    </p>
    <p>
        <input type="button" value="확인">
        <input type="button" value="취소">
    </p>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/Selector_Type.png">

### 문자열 선택자


```Java
 /*
 <table>
    <thead>
        <tr>
            <th>선택자</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>선택자[속성^=값]</td>
            <td>지정한 값으로 시작하는 요소를 선택 (startsWith)</td>
        </tr>
        <tr>
            <td>선택자[속성$=값]</td>
            <td>지정한 값으로 끝나는 요소를 선택 (endsWith)</td>
        </tr>
        <tr>
            <td>선택자[속성*=값]</td>
            <td>지정한 값을 포함하는 요소를 선택 (contains)</td>
        </tr>
    </tbody>
</table>
*/
```

<img src="https://hakcoding.github.io/img/String_Selector.png">

### 상태 선택자


```Java
// <style>
//        input[type="text"] {
//            all: unset;
//            border-bottom: 2px solid black;
//            padding: 10px;
//            background-color: #eee;
//            
//            width: 100px;
//            transition-duration: 0.5s;
//        }
//        input[type="text"]:focus {   /* 클릭하거나 키보드로 선택하여 포커스를 받고 있는 요소 */
//            transition-duration: 0.5s;
//            width: 200px;
//        }
//        input[type="text"]:active {  /* 마우스로 클릭하고 있는 동안에만 적용되는 속성 */
//            background-color: white;
//            border-bottom: 2px solid hotpink;
//        }
//        input[type="text"]:hover {   /* 클릭 없이 마우스를 올려둘 경우에 적용되는 속성 */
//            cursor: pointer;
//            background-color: lightpink;
//        }
//        input[type="text"]:disabled {    /* 비활성화된 요소에 대해서 적용되는 속성 */
//            background-color: black;
//            color: white;
//        }
//        label {
//            user-select: none;
//        }
//        input[type="checkbox"] {
//            width: 40px;
//            height: 40px;
//            appearance: none;
//            border-radius: 50%;
//            border: 1px solid black;
//            background-color: white;
//        }
//        input[type="checkbox"]:checked {
//            background: lime;
//        }
//    </style>
//</head>
//<body>
//    <h1>상태 선택자</h1>
//    <hr>
//    
//    <div class="wrap">
//        <p><input type="text" name="t1" placeholder="첫번째 입력"></p>
//        <p><input type="text" name="t2" placeholder="두번째 입력"></p>
//        <p><input type="text" name="t3" placeholder="세번째 입력"></p>
//        <p>
//            <label>
//                <input type="checkbox" name="t4" checked>네번째 입력
//            </label>
//        </p>
//        <p><input type="text" name="t5" value="고정값" disabled></p>
//        <p>
//            <select name="" id="">
//                <option>네트워크</option>
//                <option selected>시스템</option>
//                <option>개발</option>
//            </select>
//        </p>
//    </div>
//    
//</body>
```

Status_Selector<img src="https://hakcoding.github.io/img/Status_Selector.png">
