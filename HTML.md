# html 내부

### head

<head>  
    설정/ 정보
</head>



### tag

태그의 구조

<태그명 속성명="속성값"> -> 시작태그

​	내용

</태그명> -> 끝태그



시작태그~끝태그 : 요소(Element)



**시맨틱 마크업**

- 태그의 의미를 살려 코딩



**태그는 기본적으로 소문자로 작성한다.**



## id / class

- id와 class는 유사한 형태를 띄나 id가 class보다 우선적으로 적용된다.
- id는 중복이 불가하다.



## name







3월 3일 과제

작성 후 baroq8820006@gmail.com 으로 전송

작성 파일명 : 본인이름.html

기술할 내용



소개 h1

1. 이름 h2
2. 반이름 h2
3. 나이 h2
4. 좋아하는 음식 순서 5가지와 각각의 레시피 페이지 링크(ol, a href) 
5. 좋아하는 음식 중 하나의 레시피(재료, 조리순서)를 목록으로 표기(ol)

h1은 반드시 하나만 있어야함





-------



브라우저가 서버에게 요청시

HTTP 서버를 갖고있는 서버는 html 응답을 보내준다



---------------



------------------------

파라미터 전송 연습 서버 : tomcat



## 입력 양식 태그

```html
<form action="">
    <input type="color" name="mycolor" id=""><br>
	<input type="submit" value="전송">
</form>
```

- action 값이 비어 있으면 자기 자신에서 전송하게 되어 있다.
- action에 넣는 값은 아래와 같다.



in jsp

```jsp
<body>

JSP TEST <br>
 mycolor = ${ param.mycolor }
</body>
```



in html

```html
<form action="http://localhost:8081/form_jsp/form_res.jsp">
    <input type="color" name="mycolor" id=""><br>
	<input type="submit" value="전송">
</form>
```





### input 태그

```html
<input type="color" name="mycolor" id=""><br>
<input type="date" name="mydate" id="" required="required"><br>
<input type="text" name="" id=""><br>
<input type="search" name="" id=""><br>
<input type="submit" value="전송">
```

- 입력을 받는 태그이다.
- **[중요] name 속성값이 없으면 전송이 되지 않는다.**
- 'not null' 적용시, required="required" 를 통해 가능하다.
  - HTML5를 지원하는 브라우저에서만 적용됨
- vsc 플러그인 설치시 input:type 으로 단축키 사용이 가능하다.



## textarea 태그

```html
<textarea name="" id="" cols="30" rows="10">내용</textarea>
```

- cols : 가로 글자 수
- rows : 세로 글자 수
- 시작태그와 끝태그사이는 반드시 붙어야 한다.



```html
<textarea name="" id="" cols="30" rows="10">
	내용
</textarea>
```

- 위와 같이 작성시 '내용' 글자 앞에 공백까지 포함하여 전달된다.



## select 태그

```html
<label for="fav_food">좋아하는 분식은?</label>
<select name="fav_food" id="fav_food">
	<option value="0">김밥</option>
	<option value="1">떡볶이</option>
	<option value="2">순대</option>
</select>
```

- 선택이 가능한 리스트로 나온다.

- value 값 지정시, 전송되는 값은 value값으로 전달된다.

- label은 form내에서 사용하는 제목태그로서, 

  form내에서는 h태그를 제목으로 사용하지 않도록 하자.

  - label내의 'for'는 입력 양식의 제목을 뜻한다.

  - for의 값은 form 태그 내 id 값을 가진다.

  - 주로 라디오 버튼이나 체크박스에서 사용한다.

    ```html
    <label for="">성별은?</label>
    <input type="radio" name="gender" id="male_gen">
    <label for="male_gen">남남남남남남남남남남남</label>
    <input type="radio" name="gender" id="female_gen">
    <label for="female_gen">여여여여여여여여여여여</label><br>
    ```

    



## fieldset 태그 / legend 태그

```html

```

- 영역을 구분지을 때 사용한다.
  - 입력 양식에 대한 구분을 짓는 용도 : fieldset
  - 입력 영역을 구분 지을때 영역에 대한 제목 : legend
- 로그인창이나 가입양식 등에서 사용한다.



## 공간 분할 태그

- Block 타입 : 앞뒤 줄바꿈

  - 폭, 높이 조절가능

  - ```html
    <div></div>
    ```

- INLINE 타입 : 줄바꿈 없음(같은 줄에 이어서 그려짐)

  - 폭, 높이 조절 불가능

  - ```html
    <span></span>
    ```

- 공간 분할 태그는 의미상으로만 분할된다는 의미일 뿐, 실제로 눈에 보이게끔 나눌 수는 없다.



### 시맨틱 구조 태그

- header
- nav
- aside
- section
- article
- footer