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

- 이거 아주 중요하다 ★★★ -김영환 강사님-



```html
<head>
    <style>
        div{
            width: 100px; 
            height: 100px; 
            background: orange; 
            padding: 5px;
            margin: 10px;    
        }
        <!-- margin은 더 두꺼운걸 기준으로 크기가 정해진다-->
        div:nth-child(1){
            margin: 25px;
        }
    </style>
</head>
<body>
    <div>1</div>
    <div>2</div>
</body>
```



> tip. margin: 0 auto;
>
> - 0은 상하, 오토는 좌우.
> - 동일 배분 - 가운데 정렬



### 테두리 속성 - border

```css
<style>
        body {
            background: url("https://pbs.twimg.com/profile_images/864131062439436288/lLrt8xq2_400x400.jpg");
        }
        div{
            width: 100px; 
            height: 100px; 
            padding: 5px;
            margin: 10px;
            /* background: linear-gradient(greenyellow, orange); */
            background: radial-gradient(white, greenyellow);
            border: ridge cornflowerblue 5px;
            border-radius: 50px 50px 50px 50px;
        }
        div:nth-child(1){
            margin: 5px;
            background-attachment: unset;
        }
    </style>
```

- border: ridge cornflowerblue 5px;의 경우

  각 값은 중복이 되지 않는다.



### 폰트 속성

- em : 폰트 크기의 배수
- px : 픽셀
- %



#### font-family

폰트 이름을 뜻한다. 즉, 글씨체.



#### line-height

```css
<style>
	
</style>
```





### 위치 속성

#### position 속성

- static : 태그가 위에서 아래대로 순서대로 배치
- relative : 초기 위치에서 상하 좌우로 위치 이동
- fixed : 
- absolute : 원래 할당받은 자리 기준이 아닌, 자신을 둘러싼 부모 태그 중에 포지션이 absolute거나 relative인 부모를 기준으로 한다.

위치 이동을 하고자 할때는 일반적으로 relative 혹은 fixed를 사용한다.



```css
<head>
	<style>
        div{
            width: 150px; height: 100px;
        }
        #d1{
            background: linear-gradient(orange, salmon) ;
        }
        #d2{
            background: linear-gradient(salmon, teal) ;
            left: 50px;
            top: 50px;
            position: absolute;
        }
        #d3{
            background: linear-gradient(teal, orange) ;
        }
    </style>
</head>
<body>
    <div id="d1">111</div>
    <div id="d2p">
        <div id="d2">222</div>
    </div>
    <div id="d3">333</div>
</body>
```

- 위의 코드에서 d2와 d2p의 상관관계를 생각해보자
- **[중요] absolute 포지션을 주기 위해서는 반드시 그 부모 태그를 만들고, 부모 태그에 relative를 주면 된다.** 반드시 정의되는 사용법은 아니지만 이게 편한 방법이다.



> tip. 태그를 우측으로 보내는 방법 3가지
>
> 1. float: right;
> 2. position : relative;
> 3. position : absolute;



> tip2. margin, padding 크기부여 순서
>
> 상 -> 우 -> 하 -> 좌(시계방향)
>
> - 상 / 우 / 하 / 좌
> - 상 / 좌우 / 하
> - 상하 / 좌우
> - 상하좌우





#### z-index

- z-index는 크기가 클수록 높이 올라간다.

  여기서 말하는 높이는 화면상 앞뒤 위치 순서를 뜻한다.



#### overflow 속성





### clear

```css
#content{
	background: lightgoldenrodyellow;
    width: 350px;
    height: 400px;
    /* margin-left: 150px; */
    /* padding-left: 150px; */
    clear: left;
}
```

- float:left를 선언한 구역과 중복(겹침)이 발생하지 않는다



### 변형 속성 기본

- transition : 모든 transition 속성 사용
- transition-delay : 이벤트 발생 후 몇 초 후에 재생할지 지정
- transition-duration : 몇 초 동안 재생할지 지정
- transition-property : 어떤 속성을 변형할지 지정
- transition-timing-function : 수치 변형 함수를 지정



#### transition-delay 속성

- 이벤트가 발생하고 몇 초 동안 기다린 후 애니메이션이 작동할지 지정하는 속성
- 시간 단위는 주로 ms, s를 사용한다.



#### transition-timing-fuction 속성

각 속성은 속도 변화 구간이 다르다. (f : fast, s : slow)

- linear (common) : 보통 자주 쓰임
- ease (c-f)
- ease-in (s-f)
- ease-in-out (s-f-s)
- ease-out (f-s)



#### 애니메이션 속성

- animation
- animation-delay
- animation-direction
- animation-duration
- animation-iteration-count
- animation-name
- animation-play-state : 애니메이션을 중지하고, 
- animation-timing-function



선언은 keyframe, 적용은 animation에서 진행한다.

```css
#box{
    animation-name: rint;
    animation-duration : 2s;
}

@keyframes rint {
    from{left:0; transform: rotate(0deg);}
	50% { left:500px;}
    to { 
        left: 500px;
        transform: rotate(360deg);
	}
}
```







## 변환





### 반응형 웹

```css
<link rel="stylesheet" href="desktop.css" media="screen"/>
<link rel="stylesheet" href="print.css" media="print"/>
```

- media : CSS를 적용할 디바이스를 지정하는 형식

  즉, 스타일시트가 특정한 디바이스에서만 작동하게 만든다.

  - aural : 음성 발생장치(TTS: Text To Speech)
  - braille : 점자 출력 장치
  - handheld : 전자사전 형태의 컴퓨터
  - print
  - projection
  - screen : PC 화면
  - tty : 더미 터미널, tele type writer(전보)
  - tv



```css
@media print {
	#foot{
    	display: none;
	}
}
```



#### 화면 방향 전환

Longitude: 경도

latitude : 위도



