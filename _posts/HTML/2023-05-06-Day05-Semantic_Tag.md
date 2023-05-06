---
layout: single
title: "Semantic Tag"
categories: HTML
author_profile: true
toc: true
author_profile: false
---

# semantic 태그


```Java
/* 
 <ul>
        <li>header : 문서의 상단을 나타낸다</li>
        <li>nav : 메뉴 네비게이터</li>
        <li>aside : 사이드 메뉴</li>
        <li>main : 페이지 주 내용</li>
        <li>section : 일정 영역</li>
        <li>article : 단락</li>
        <li>footer : 페이지 하단 고정 내용</li>
    </ul>

    <blockquote style="background-color: burlywood; padding: 20px;">
        &lt;div class="header">&lt;/div><br>
        &lt;header>&lt;/header><br>
        <!--    &lt; : less than, 작다를 의미하는 부등호 기호-->
        공백기호&nbsp;1234
    </blockquote>

    <style>
        header  { border: 3px dashed red;       }
        nav     { border: 3px dashed orange;    }
        main    { border: 3px dashed lime;      }
        section { border: 3px dashed blue;      }
        article { border: 3px dashed skyblue;   }
        footer  { border: 3px dashed purple;    }

        main {
            display: flex;
        }
        section {
            flex: 1;
        }
    </style>

    <header>
        <h3 class="logo">logo</h3>
        <nav>
            <ul>
                <li>메뉴1</li>
                <li>메뉴2</li>
                <li>메뉴3</li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="left">
            <article>1</article>
            <article>2</article>
            <article>3</article>
        </section>
        <section class="right">
            <article>4</article>
            <article>5</article>
            <article>6</article>
        </section>
    </main>

    <footer>
        copyright...
    </footer>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/Semantic_Tag.png">

### Z-index


```Java
 /*
 <style>
        .wrap {
            border: 3px solid silver;
            width: 150px;
            height: 150px;
            position: relative;
        }
        .item {
            width: 100px;
            height: 100px;
            position: absolute;
        }
        .red {
            top: 0;
            left: 0;
            background-color: red;
            z-index: 1;
        }
        .blue {
            bottom: 0;
            right: 0;
            background-color: blue;
            // z-index: 0; 
        }
    </style>
</head>
<body>

    <h1>ex02.html : z-index</h1>
    <hr>
    <h3>x축 y축으로 위치를 지정했을 때, 요소가 겹친다면 어떤 요소를 앞에 둘지 결정한다</h3>

    <div class="wrap">
        <div class="item red"></div>
        <div class="item blue"></div>
    </div>
    
</body>
*/
```

<img src="https://hakcoding.github.io/img/z-index.png">
