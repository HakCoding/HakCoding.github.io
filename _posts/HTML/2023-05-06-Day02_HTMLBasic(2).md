---
layout: single
title: "HTML_Basic(2)"
categories: HTML
author_profile: true
toc: true
author_profile: false
---

# HTML 기본 문법 (2)

### input

<fieldset>
        <ul>
            <li>사용자의 입력을 서버에 전달할 수 있다</li>
            <li>직접 입력하거나, 객관식 형식으로 선택하게 할 수 있다</li>
            <li>type 속성으로 어떤 유형의 값을 전달하는지 지정할 수 있다</li>
            <li>type에 따라 사용하는 세부 속성이 조금씩 다르다</li>
            <li>name 속성으로 전달하는 값의 이름을 지정한다</li>
            <li>서버에서 받을 때 name으로 구분한다</li>
            <li>입력값은 value속성의 값으로 처리된다</li>
            <li>value를 미리 지정할 수도 있다</li>
        </ul>
    </fieldset>


```Java
/*
<table border="1" cellpadding="10" cellspacing="0">
<thead>
    <tr>
        <th>type</th>
        <th>예시</th>
        <th>설명</th>
    </tr>
</thead>
<tbody>
    <tr>
        <td>text</td>
        <td>
            <input type="text" name="t1" placeholder="안내 메시지"><br>
            <input type="text" name="t2" value="미리 입력된 값">
        </td>
        <td>기본값, 문자열 형식을 입력받는다</td>
    </tr>
    <tr>
        <td>number</td>
        <td>
            <input type="number" name="t3" min="0" max="100" step="5"><br>
            <input type="number" name="t4" value="1234" step="0.1">
        </td>
        <td>숫자, 정수 및 실수. 최소/최대값과 증감값의 단위를 지정할 수 있다</td>
    </tr>
    <tr>
        <td>range</td>
        <td>
            <input type="range" name="t5" min="0" max="100">
            <span class="rangeValue"></span>
            <br>
            <input type="range" name="t6" value="100">
            <span class="rangeValue"></span>
        </td>
        <script>
            const rangeList = document.querySelectorAll('input[type="range"]')
            rangeList.forEach(r => {
                const span = r.nextElementSibling
                span.innerText = r.value
                r.onchange = (event) => {
                    span.innerText = event.target.value
                }
            })
        </script>
        <td>숫자, 0 ~ 100 사이 정수를 처리한다</td>
    </tr>
    <tr>
        <td>radio</td>
        <td>
            <input type="radio" name="t7" value="red">빨강<br>
            <input type="radio" name="t7" value="green">초록<br>
            <label><input type="radio" name="t7" value="blue">파랑</label>
        </td>
        <td>정해진 값 중에서 하나를 고르게 한다</td>
    </tr>
    <tr>
        <td>checkbox</td>
        <td>
            <input type="checkbox" name="t8" value="red">빨강<br>
            <input type="checkbox" name="t8" value="green">초록<br>
            <label><input type="checkbox" name="t8" value="blue">파랑</label>
        </td>
        <td>정해진 값 중에서 여러항목을 고르게 한다</td>
    </tr>
    <tr>
        <td>date</td>
        <td>
            <input type="date" name="t9" value="2023-04-19"><br>
        </td>
        <td>연월일 단위의 날짜를 선택하게 한다</td>
    </tr>
    <tr>
        <td>time</td>
        <td>
            <input type="time" name="t10" value=""><br>
        </td>
        <td>오전/오후 시:분 형식으로 입력받는다</td>
    </tr>
    <tr>
        <td>datetime-local</td>
        <td>
            <input type="datetime-local" name="t11" value=""><br>
        </td>
        <td>date + time 의 형식</td>
    </tr>
    <tr>
        <td>color</td>
        <td>
            <input type="color" name="t12"><br>
        </td>
        <td>색상을 선택하게 한다</td>
    </tr>
    <tr>
        <td>password</td>
        <td>
            <input type="password" name="t12" value="itbank"><br>
        </td>
        <td>문자열을 마스킹하여 입력받는다</td>
    </tr>
    <tr>
        <td>email</td>
        <td>
            <form>
            <input type="email" name="t13" placeholder="메일 주소 입력">
            <button>확인</button>
            </form>
        </td>
        <td>이메일 주소 형식의 문자열을 입력받는다</td>
    </tr>
    <tr>
        <td>search</td>
        <td>
            <input type="search" name="t13" placeholder="검색어 입력"><br>
        </td>
        <td>검색어 입력 후 우측에 x버튼으로 글자 삭제 가능</td>
    </tr>
    <tr>
        <td>select</td>
        <td>
            <select name="t14">
                <option value="e">초등학생</option>
                <option value="m">중학생</option>
                <option value="h">고등학생</option>
                <option value="u">대학생</option>
            </select>
        </td>
        <td>radio와 유사하게 여러 값 중 하나를 입력받는다</td>
    </tr>
    <tr>
        <td>textarea</td>
        <td>
            <textarea name="t15">미리 입력된 값</textarea>
        </td>
        <td>여러줄의 문자열을 입력받기 위해서 사용한다</td>
    </tr>
    <tr>
        <td>file</td>
        <td>
            <input type="file" name="t16">
        </td>
        <td>사용자가 파일을 첨부할 수 있도록 한다</td>
    </tr>
</tbody>
</table>
*/
```

<table border="1" cellpadding="10" cellspacing="0">
        <thead>
            <tr>
                <th>type</th>
                <th>예시</th>
                <th>설명</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>text</td>
                <td>
                    <input type="text" name="t1" placeholder="안내 메시지"><br>
                    <input type="text" name="t2" value="미리 입력된 값">
                </td>
                <td>기본값, 문자열 형식을 입력받는다</td>
            </tr>
            <tr>
                <td>number</td>
                <td>
                    <input type="number" name="t3" min="0" max="100" step="5"><br>
                    <input type="number" name="t4" value="1234" step="0.1">
                </td>
                <td>숫자, 정수 및 실수. 최소/최대값과 증감값의 단위를 지정할 수 있다</td>
            </tr>
            <tr>
                <td>range</td>
                <td>
                    <input type="range" name="t5" min="0" max="100">
                    <span class="rangeValue"></span>
                    <br>
                    <input type="range" name="t6" value="100">
                    <span class="rangeValue"></span>
                </td>
                <script>
                    const rangeList = document.querySelectorAll('input[type="range"]')
                    rangeList.forEach(r => {
                        const span = r.nextElementSibling
                        span.innerText = r.value
                        r.onchange = (event) => {
                            span.innerText = event.target.value
                        }
                    })
                </script>
                <td>숫자, 0 ~ 100 사이 정수를 처리한다</td>
            </tr>
            <tr>
                <td>radio</td>
                <td>
                    <input type="radio" name="t7" value="red">빨강<br>
                    <input type="radio" name="t7" value="green">초록<br>
                    <label><input type="radio" name="t7" value="blue">파랑</label>
                </td>
                <td>정해진 값 중에서 하나를 고르게 한다</td>
            </tr>
            <tr>
                <td>checkbox</td>
                <td>
                    <input type="checkbox" name="t8" value="red">빨강<br>
                    <input type="checkbox" name="t8" value="green">초록<br>
                    <label><input type="checkbox" name="t8" value="blue">파랑</label>
                </td>
                <td>정해진 값 중에서 여러항목을 고르게 한다</td>
            </tr>
            <tr>
                <td>date</td>
                <td>
                    <input type="date" name="t9" value="2023-04-19"><br>
                </td>
                <td>연월일 단위의 날짜를 선택하게 한다</td>
            </tr>
            <tr>
                <td>time</td>
                <td>
                    <input type="time" name="t10" value=""><br>
                </td>
                <td>오전/오후 시:분 형식으로 입력받는다</td>
            </tr>
            <tr>
                <td>datetime-local</td>
                <td>
                    <input type="datetime-local" name="t11" value=""><br>
                </td>
                <td>date + time 의 형식</td>
            </tr>
            <tr>
                <td>color</td>
                <td>
                    <input type="color" name="t12"><br>
                </td>
                <td>색상을 선택하게 한다</td>
            </tr>
            <tr>
                <td>password</td>
                <td>
                    <input type="password" name="t12" value="itbank"><br>
                </td>
                <td>문자열을 마스킹하여 입력받는다</td>
            </tr>
            <tr>
                <td>email</td>
                <td>
                    <form>
                    <input type="email" name="t13" placeholder="메일 주소 입력">
                    <button>확인</button>
                    </form>
                </td>
                <td>이메일 주소 형식의 문자열을 입력받는다</td>
            </tr>
            <tr>
                <td>search</td>
                <td>
                    <input type="search" name="t13" placeholder="검색어 입력"><br>
                </td>
                <td>검색어 입력 후 우측에 x버튼으로 글자 삭제 가능</td>
            </tr>
            <tr>
                <td>select</td>
                <td>
                    <select name="t14">
                        <option value="e">초등학생</option>
                        <option value="m">중학생</option>
                        <option value="h">고등학생</option>
                        <option value="u">대학생</option>
                    </select>
                </td>
                <td>radio와 유사하게 여러 값 중 하나를 입력받는다</td>
            </tr>
            <tr>
                <td>textarea</td>
                <td>
                    <textarea name="t15">미리 입력된 값</textarea>
                </td>
                <td>여러줄의 문자열을 입력받기 위해서 사용한다</td>
            </tr>
            <tr>
                <td>file</td>
                <td>
                    <input type="file" name="t16">
                </td>
                <td>사용자가 파일을 첨부할 수 있도록 한다</td>
            </tr>
        </tbody>

    </table>

### div & span


```Java
/*
<style>
        div {
            border: 1px solid red;
        }
        span {
            border: 1px solid blue;
        }
        div, span {
            margin: 5px;
            padding: 5px;
        }
    </style>
</head>
<body>

    <h1>div와 span</h1>
    <hr>

    <div>div1</div>
    <div>div2</div>
    <div>div3</div>
    
    <span>span1</span>
    <span>span2</span>
    <span style="width: 300px;">span3</span>
    
    <div style="width: 300px;">div4</div>
    <div>div5</div>
    <div>div6</div>

    <fieldset>
        <legend>display: inline</legend>
        <ul>
            <li>한 줄 안에 여러 요소를 구분하여 배치할 때 사용한다</li>
            <li>대표적으로 span이 있다</li>
            <li>크기를 직접 지정할 수 없다</li>
        </ul>
    </fieldset>
    <br>
    <fieldset>
        <legend>display: block</legend>
        <ul>
            <li>줄 단위로 구분되는 영역을 생성할 때 사용한다</li>
            <li>block 요소는 혼자서 한 줄을 차지한다 (h1, div, p ...)</li>
            <li>너비와 높이를 직접 지정할 수 있다</li>
        </ul>
    </fieldset>
    <br>
    <fieldset>
        <legend>display: inline-block</legend>
        <ul>
            <li>inline 처럼 한 줄에 여러 요소를 배치할 수 있다</li>
            <li>block 처럼 너비와 높이를 직접 지정할 수 있다</li>
            <li>크기를 지정하여 여러 요소를 한 줄에 배치하고 싶을 때 사용한다</li>
        </ul>
    </fieldset>

</body>
</html>
*/
```
<img src="img/div&span.png">
