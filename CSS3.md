# CSS

> Cascading Style Sheet

- 계단식으로 정의됨
- 즉, 우선순위가 존재하고 우선순위는 위에서부터 아래로 정의된다.
- 선택자 / 속성



CSS는 외우기보단 필요할 때 찾아서 쓰는 식으로 활용하자.



## 선택자

```css
h1{color:red;}
```

- h1 : 선택자
- color : 
- red : 



### 선택자의 종류

- **태그 선택자**
- **아이디 선택자**
- **클래스 선택자**
- **후손 선택자(자손 선택자를 포함)**
- **자손 선택자(자식 선택자)**
- 속성 선택자
- 동위 선택자, 구조 선택자, 상태, 링크, 문자, 부정 등



선택자의 가장 기본적인 해석 방법은 **'페이지 내에 존재하는 모든'**이 앞에 붙는다.



### 태그 선택자

```css
<head>
	<style>
    	h1{color:red;}
    	p{color: blue;}
	</style>
</head>
<body>
    <h1>첫번째 CSS</h1>
    <p>CSS는 화면을 꾸미는 기술입니다</p>
</body>
```



### 아이디 선택자

```css
<head>
	<style>
		h1{color:red;}
        p{color: blue;}
        #p2{color: green; background-color: yellow;}
    </style>
</head>
<body>
    <h1>첫번째 CSS</h1>
    <p>CSS는 화면을 꾸미는 기술입니다</p>
    <p id="p2">CSS는 화면을 꾸미는 기술입니다</p>
</body>
```

- **#이 ID 속성값이다.**
- **ID 값은 동일 페이지내에서 중복되면 안된다.**
- 오류는 발생하지 않지만 JavaScript나 jQuery 연산시 문제 발생할 수 있다.



### 클래스 선택자

```html
<ul>
    <li class="select">Lorem ipsum</li>
</ul>
```

- 위에서 class가 style 명이다.



```css
/* 선언부 */
<style>
	.select { color : red; }
</style
```

- **[.클래스명] 을 통해 클래스 속성에 적용**할 수 있다.
- 아이디 선택자는 하나만 있을 때 사용하고, 클래스 선택자는 반복적으로 쓸 때 사용한다.



#### 태그명.클래스 

```css
<style>
	ul.select { color : red; }
</style
```

- 적용 타깃을 축소할 수 있다.
- 위의 사례에선 모든 select에 적용되지 않고, select 의 ul 리스트에만 적용된다.





### 속성 선택자

```html
<form action="">
    <input type="text" name="" id="">
	<input type="date" name="" id="">
</form>
```

- type의 속성 값을 지정하는 방법이다.



```css
<style>
	input[type=text]{border: 3px dotted red;}
	input[type=date]{border: 5px dotted blue;}
</style>
```





### 자손 선택자 / 후손 선택자

```html
<head>
    <style>
        ul > li{color: red;}
        li{color: blue;}
    </style>
</head>
<body>
    <h1>후손과 자손</h1>
    <h2>좋아하는 가수들</h2>
    <ul>
        <li>현미</li>
        <li>현숙</li>
        <li>현철</li>
    </ul>

    <h2>프로그래밍 언어</h2>
    <ol>
        <li>자바</li>
        <li>파이썬</li>
    </ol>
</body>
```

- 꺾쇠를 넣으면 자손, 없으면 후손을 가리킨다.

- 후손은 해당 자손을 포함하여 자손의 자손까지 가리킨다.

- 위의 선택자 사례에서 li의 색깔은 충돌이 일어나는데 이때, CSS 선택자 가중치가 적용된다.

  - 마지막으로 적용된 걸 우선으로 적용하여

    ul의 li는 red, ol의 li는 blue color를 가진다.



### Cascading 규칙

> 이건 몰라도 됨.. 디자이너가 아니기 때문에...

예를들어 

CSS 선택자 가중치

태그 선택자 : 1

클래스 선택자 : 10

- ```css
  <style>
  	.singers > li{color:red;} /*가중치 11*/
  	body > ul > li {color:blue;} /*가중치 3*/
  </style>
  ```

  

아이디 선택자 : 100



마지막으로 선언한걸 우선적으로 적용한다.

또 선택자를 많이 쓸수록 우선 순위가 높다.

- ```css
  <style>
  	body > ul > li{color: red;}
  	body li{color:blue;}
  </style>
  ```

  

### 동위 선택자(Sibling - 형제)

- 선택자A + 선택자B : 선택자A 뒤에 나오는 선택자B를 의미
- 선택자A ~ 선택자B : 선택자A 뒤에 나오는 모든 선택자B



동위 선택자는 단독적으로 쓰이지 않고 반응 선택자와 함께 쓰인다.

```css
<style>
	h1 + h2{background-color: yellow;}
	h3 ~ h4{background-color: orange;}
</style>
```



### 반응 선택자

- [:active] : 사용자가 마우스로 클린한 태그를 선택
- [:hover] : 사용자가 마우스를 올린 태그를 선택

```css
h1:hover{border: 3px dashed red;}
```

  tip. 같은 기능을 자바스크립트로 할 수 있다.



- 동위 선택자와 함께 사용한 경우

  ```css
  h1:hover + h2{border: 3px dashed red;}
  ```

  



### 상태 선택자

- [:checked] : 
- [:focus] : 
- [:enabled] : 
- [:disabled] : 

- 주로 설명서를 정의할 때 많이 사용한다.



```css
<style>
	input + span{display: none;}
    input:focus + span{display: inline;}
</style>
```



```html
<form action="">
	이름:<input type="text">
    <span>이름을 입력해주세요</span><br>
    주소:<input type="text">
    <span>주소를 입력해주세요</span><br>
    나이:<input type="text">
    <span>나이를 입력해주세요</span>
</form>
```





### 구조 선택자

```css
<style>
	table > tbody > tr{background: orange;}
    tbody > tr:first-child {background: beige;}

	<!--짝수번째 -->
	tbody > tr:first-child > td:nth-child(2n){} 
</style>
```



### 링크 선택자

> 자주 사용하는 선택자이므로, 자주 보도록 하자

- [:link] : href 속성을 가지고 있는 a 태그를 선택
- [:visited] : 방문했던 링크를 가지고 있는 a 태그를 선택



```css
<style>
	a:link{text-decoration: none;}
    a:hover{text-decoration: underline;}
</style>

<body>
	<a href="https://www.naver.com">네이버</a>
</body>
```





## 속성



### 박스 속성

- 이거 아주 중요하다 -김영환 강사님-