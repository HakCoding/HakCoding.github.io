---
layout: single
title: "JAVAscript"
categories: HTML
author_profile: true
toc: true
author_profile: false
---

# 자바스크립트


```Java
/*
<style>
        input[type="text"] {
            all: unset;
            padding: 10px;
            font-size: 20px;
            border-bottom: 2px solid black;
            background-color: #fafafa;
        }
    </style>
</head>
<body>
    
    <h1>ex01.html</h1>
    <hr>

    <input type="text" placeholder="입력" value="입력된 값" autofocus>
    <input type="password">
    <input type="button" value="버튼1">
    <button>버튼2</button>

    <pre class="text"></pre>

    <script>
        // HTML 문서에서 특정 요소 (element)를 불러오기 위해서 css 선택자를 사용한다
        
        // document.getElementById(id)      : id를 지정하여 단일 요소를 불러온다
        // document.querySelector(selector) : css 선택자를 지정하여 단일 요소를 불러온다
        // document.querySelectorAll(selector) : 선택자에 맞는 모든 요소를 불러온다

        // var, let, const
        const input1 = document.querySelector('input[type="text"]')
        const input2 = document.querySelector('input')
        const input3 = document.querySelector('input[type="password"]')
        const input4 = document.querySelector('input[type="button"]')
        const inputList = document.querySelectorAll('input')

        const pre = document.querySelector('pre.text')

        // alert(input1 == input2)

        pre.style.backgroundColor = 'skyblue'
        pre.style.padding = '20px'
        pre.style.fontSize = '20px'
        pre.innerText = '안녕하세요\n'
        pre.innerText += '자바스크립트를 이용하여 작성한 내용입니다\n'
        pre.innerText += 'input1 == inputList[0] : ' + (input1 == inputList[0]) + '\n'
        pre.innerText += 'input3 == inputList[1] : ' + (input3 == inputList[1]) + '\n'
        pre.innerText += 'input4 == inputList[2] : ' + (input4 == inputList[2]) + '\n'

        for(let i = 0; i < inputList.length; i++) {
            const target = inputList[i]
            target.value = 'Hello ' + i + ' !!'
        }

    </script>

</body>
*/
```

<img src="https://hakcoding.github.io/img/JAVAscript.png">

### 자바스크립트 입력 


```Java
/*
<body>

    <h1>ex02.html</h1>
    <hr>
    <div class="form">
        <p><input type="text" name="id" placeholder="아이디"></p>
        <p><input type="password" name="pw" placeholder="비밀번호"></p>
        <p><input type="submit"></p>
    </div>

    <div class="result"></div>

    <script>
        // 버튼 클릭 이벤트
        const submit = document.querySelector('input[type="submit"]')

        submit.onclick = function() {
            // alert('버튼 클릭 !!')
            const inputId = document.querySelector('input[name="id"]')
            const inputPw = document.querySelector('input[name="pw"]')
            const idText = inputId.value
            const pwText = inputPw.value

            const result = document.querySelector('div.result')

            result.innerHTML += '<p>입력한 아이디 : ' + idText + '</p>'
            result.innerHTML += '<p>입력한 비밀번호 : ' + pwText + '</p>'
            
            result.style.border = '5px solid red'
            result.style.backgroundColor = 'yellow'
            result.style.padding = '20px'
        }
    </script>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/JAVAscript.pnginput.png">

### 자바스크립트 클릭


```Java
/*
<style>
        #root {
            border: 2px solid black;
            width: 500px;
        }
        ul.tab {
            display: flex;
            list-style: none;
            padding-left: 0;
            margin: 0;
            height: 50px;
        }
        ul.tab > li {
            flex: 1;
            text-align: center;
            padding: 10px;
            cursor: pointer;
            border: 1px solid grey;
        }
        ul.tab > li.selected {
            border-bottom: 0;
        }
        div.box {
            position: relative;
            width: 100%;
            height: 300px;
        }
        div.box > div {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            box-sizing: border-box;
            padding: 20px;
            font-size: 70px;
        }
        ul.tab > li:nth-child(1),
        div.box > div:nth-child(1) { 
            background-color: pink; 
        }
        ul.tab > li:nth-child(2),
        div.box > div:nth-child(2) { 
            background-color: lightgoldenrodyellow;
        }
        ul.tab > li:nth-child(3),
        div.box > div:nth-child(3) { 
            background-color: skyblue;
        }

        ul.tab > li {
            border-bottom: 2px solid silver;
        }
        ul.tab > li.selected {
            border-bottom: 0;
        }
        div.box > div {
            display: none;
        }
        div.box > div.selected {
            display: block;
        }

    </style>
</head>
<body>

    <h1>상단 탭에 따라서 다른 내용이 나타나는 메뉴</h1>
    <hr>

    <div id="root">
        <ul class="tab">
            <li class="selected">menu1</li>
            <li>menu2</li>
            <li>menu3</li>
        </ul>
        <div class="box">
            <div class="menu1 selected">menu1</div>
            <div class="menu2">menu2</div>
            <div class="menu3">menu3</div>
        </div>
    </div>

    <script>
        // nodeList
        const tabList = document.querySelectorAll('ul.tab > li')
        const boxList = document.querySelectorAll('div.box > div')

        tabList.forEach((element, index) => {
            element.onclick = function() {

                // 모든 탭의 selected 클래스를 제거한다
                tabList.forEach(e => e.classList.remove('selected'))
                boxList.forEach(e => e.classList.remove('selected'))

                // 클릭된 항목은 selected 클래스를 추가한다
                tabList[index].classList.add('selected')
                boxList[index].classList.add('selected')
            }
        })

        
//            nodeList 내부의 각 element에 대한 반복문
//           nodeList.forEach((element) => { ... })
//
//            nodeList 내부의 각 element에 대한 반복문 (index를 참조해야 할때)
//            nodeList.forEach((element, index) => { ... })
//
//            for(let i = 0; i < nodeList.length; i++) {
//                const element = nodeList[i]
//                ...
//            }
        
    </script>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/menu1.png" width="300px" height="300px">
<img src="https://hakcoding.github.io/img/menu2.png" width="300px" height="300px">
<img src="https://hakcoding.github.io/img/menu3.png" width="300px" height="300px">
