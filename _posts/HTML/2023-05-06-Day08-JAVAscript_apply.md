---
layout: single
title: "JAVAscript-apply"
categories: HTML
author_profile: true
toc: true
author_profile: false
---

# 자바스크립트 응용

### 문자 입력


```Java
/*
<style>
        div.text {
            width: 300px;
            height: 400px;
            border: 2px solid black;
            overflow-x: hidden;
            overflow-y: auto;
            padding: 10px;
        }
        div.text > p {
            background-color: lightgoldenrodyellow;
            padding: 5px 10px;
            border-radius: 20px;
            box-shadow: 2px 2px 2px grey;
            width: max-content;
            max-width: 280px;
            word-wrap: break-word;  
            // 단어 단위로 구분하여 줄 바꿈 적용, 필요하면 단어도 분리한다 
        }
    </style>
</head>
<body>

    <h1>ex02.html</h1>
    <hr>
    <div class="text"></div>

    <p>
        <input type="text" id="input" autofocus>
    </p>

    <script>
        // input에 글자를 입력하고 엔터를 누르면 내용을 div.text에 추가하기
        const input = document.getElementById('input')
        const text = document.querySelector('div.text')

        input.onkeypress = function(event) {
            if(event.key == 'Enter') {                  // 엔터를 누르면
                const value = event.target.value        // 입력글자를 가져와서
                const p = document.createElement('p')   // p태그를 생성하고
                p.innerText = value                     // p태그 안에 글자를 넣어주고
                text.appendChild(p)                     // p를 div안에 추가한다
                event.target.value = ''                 // 입력했던 글자는 지운다
                
                const scrollOptoin = {
                    top: text.scrollHeight, 
                    behavior: "smooth"
                }
                text.scroll(scrollOptoin)
            }
        }
    </script>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/chatting.png"  width="300px" height="200px">

### 달력


```Java
/*
<style>
        #root {
            width: 800px;
            margin: 20px auto;
            display: flex;
            flex-flow: wrap;
            border: 5px solid black;
            box-sizing: border-box;
        }
        .red { color: red;}
        .blue{ color: blue;}
        .other {
            opacity: 0.2;
        }
        .item {
            box-sizing: border-box;
            width: calc(100% / 7);
            height: 75px;
            padding: 5px;
            border: 1px solid black;
        }
        .title {
            display: flex;
            justify-content: space-around;
        }
    </style>
</head>
<body>

    <h1>날짜를 화면에 반영하기</h1>
    <hr>
    <div class="title">
        <button><<</button>
        <h3>4월</h3>
        <button>>></button>
    </div>
    <div id="root"></div>

    <script>
        // 2023년 4월의 날짜를 div#root 에 출력하세요
        // (4월은 30일까지 있습니다)
        // 토요일은 파란색, 일요일은 빨간색으로 출력하세요
        // 각 내용은 div.item 으로 묶어서 처리하세요
        const root = document.getElementById('root')

        const myDateFormat = function(d) {
            const dayArr = ['일요일', '월요일', '화요일', '수요일', '목요일', '금요일', '토요일']
            const m = d.getMonth() + 1
            
            let result = ''
            result += `${d.getFullYear()}-`
            result += `${m < 10 ? '0' + m : m}-`
            result += `${d.getDate() < 10 ? '0' + d.getDate() : d.getDate()} `
            result += dayArr[d.getDay()]
            return result
        }

        for(let i = -5; i <= 36; i++) {
            const item = document.createElement('div')
            item.classList.add('item')
            
            // item.innerText = i
            const d = new Date(2023, 3, i)
            item.innerText = myDateFormat(d)

            if(d.getDay() == 0)     item.classList.add('red')
            if(d.getDay() == 6)     item.classList.add('blue')
            if(d.getMonth() != 3)   item.classList.add('other')

            root.appendChild(item)
        }
        
    </script>

    
</body>
*/
```

<img src="https://hakcoding.github.io/img/Calendar.png" width="800px" height="800px">

### 사진첩


```Java
/*
<style>
        #root {
            display: flex;
        }
        .item {
            width: 500px;
            height: 400px;
            background-position: center;
            background-size: auto 100%;
            background-repeat: no-repeat;
            border: 3px solid grey;
            flex: 1;
            transition-duration: 1s;
            opacity: 0.2;
            cursor: pointer;
        }
        .item.selected {
            flex: 20;
            opacity: 1;
        }
    </style>
</head>
<body>

    <h1>선택한 그림만 펼쳐보기</h1>
    <hr>
    <div id="root"></div>

    <p>
        <input type="number" name="idx" min="0" max="8" value="0">
    </p>

    <script>
        // 자바스크립트에서 참조할 데이터 혹은 문서요소(element)를 변수로 선언
        const arr = [
            'img/1.jpg',
            'img/2.jpg',
            'img/3.jpg',
            'img/4.jpg',
            'img/5.jpg',
            'img/6.jpg',
            'img/7.jpg',
            'img/8.jpg',
            'img/9.jpg',
        ]
        const root = document.getElementById('root')
        const input = document.querySelector('input[name="idx"]')

        // 연결하고 싶은 함수를 만든다
        const init = function() {   
            for(let i = 0; i < arr.length; i++) {
                const item = document.createElement('div')
                // <div></div>

                item.classList.add('item')
                // <div class="item"></div>

                item.style.backgroundImage = `url('${arr[i]}')`
                // <div class="item" style="background-image: url('img/1.jpg')"></div>

                // 스크립트로 생성한 객체는 이벤트 연결 시 document에서 찾지 않고
                // 생성하는 시점에서 이벤트를 연결한다
                item.onmouseover = mouseoverHandler

                root.appendChild(item)
            }
            // 모든 item을 추가한 이후, 0번째 요소에만 selected를 추가한다
            document.querySelector('.item').classList.add('selected')
        }

        const changeHandler = function(event) {
            const itemList = document.querySelectorAll('.item')
            itemList.forEach(item => item.classList.remove('selected'))

            const idx = event.target.value
            itemList[idx].classList.add('selected')
        }

        const mouseoverHandler = function(event) {
            const itemList = document.querySelectorAll('.item')
            itemList.forEach(item => item.classList.remove('selected'))

            event.target.classList.add('selected')
        }

        // 요소의 특정 이벤트에 함수를 연결한다
        window.onload = init
        input.onchange = changeHandler
        
    </script>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/iu1.png" width="500px" height="500px">
<img src="https://hakcoding.github.io/img/iu2.png" width="500px" height="500px">
<img src="https://hakcoding.github.io/img/iu3.png" width="500px" height="500px">
