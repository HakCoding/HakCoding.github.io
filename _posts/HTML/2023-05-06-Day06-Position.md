---
layout: single
title: "Position"
categories: HTML
author_profile: true
toc: true
author_profile: false
---

# Position


```Java
/*
<style>
        .img {
            position: relative;
        }
        h3 {
            position: absolute;
            top: 0;
            right: 0;
            font-size: 30px;
            margin-top: 20px;
            margin-right: 320px;
            color: white;
        }
        .wrap {
            background-image: url('https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAxOTExMDdfMTUz%2FMDAxNTczMTM3ODI5NTQw.4eLgS7XqFC_fPKvM6iyq4v1lHgCxmscJWVEdXx0P9ccg.9yr9-X0FgERLGdhX0v94yqrgonoUQX5EInjCR3EQupsg.JPEG.jjung1515pb%2FDSG09181.JPG&type=sc960_832');
            background-size: auto 100%;
            background-repeat: no-repeat;
            width: 640px;
            height: 400px;
            padding: 30px;
            box-sizing: border-box;
            text-align: left;
            color: white;
            font-size: 30px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h1>그림위에 글자 (position)</h1>
    <hr>

    <div class="img">
        <img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAxOTExMDdfMTUz%2FMDAxNTczMTM3ODI5NTQw.4eLgS7XqFC_fPKvM6iyq4v1lHgCxmscJWVEdXx0P9ccg.9yr9-X0FgERLGdhX0v94yqrgonoUQX5EInjCR3EQupsg.JPEG.jjung1515pb%2FDSG09181.JPG&type=sc960_832" height="400">
        <h3>맛있는 부대찌개</h3>
    </div>

    <div class="wrap">
        맛있는 부대찌개
    </div>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/position.png">

### Scale


```Java
/*
<style>
        .item {
            width: 200px;
            height: 200px;
            margin: 10px;
            border: 2px dashed blue;
            position: relative;
            text-align: center;
            overflow: hidden;
        }
        .item > h3 {
            position: absolute;
            bottom: 10px;
            right: 10px;
            margin: 0;
        }
        .item > img {
            width: 150px;
            transition-duration: 0.5s;
            cursor: pointer;
        }
        .item:hover > img {
            transform: scale(125%);
        }
        .wrap {
            display: flex;
            flex-flow: wrap;
            width: 700px;
            border: 2px dashed red;
        }
    </style>
</head>
<body>

    <h1>여러 항목 중 마우스 올린 요소에만 scale</h1>
    <hr>

    <div class="wrap">
        <div class="item">
            <img src="img/짱구.png" alt="대체 텍스트. 그림이 안뜨면 내용을 식별하기 위한 글자">
            <h3>짱구</h3>
        </div>
        <div class="item">
            <img src="img/맹구.png">
            <h3>맹구</h3>
        </div>
        <div class="item">
            <img src="img/짱아.png">
            <h3>짱아</h3>
        </div>
        <div class="item">
            <img src="img/훈이.png">
            <h3>훈이</h3>
        </div>
        <div class="item">
            <img src="img/흰둥이.png">
            <h3>흰둥이</h3>
        </div>
        <div class="item">
            <img src="img/수지.png">
            <h3>수지</h3>
        </div>
    </div>

    
</body>
*/
```

<img src="https://hakcoding.github.io/img/scale.png">
