# TIL(Today I Learned)

> 그날 공부한 내용은 그날 정리하기





# 🗓️220826

### 🌐 **브라우저 스타일 초기화하기**

👉 **Why**

: 브라우저의 기본 CSS 설정을 초기화하여 크로스 브라우징 시의 에러를 방지한다

👉 **How (VScode)**

1. reset.css cdn 검색하여 링크 복사

2. html `<head>`에 **`<link>` 태그 href에 붙여넣기** 하여 사용

   

### 🌐 부모요소와 자식요소

```jsx
<태그>
	<태그> 내용 </태그>
</태그>
```

👉 감싼 태그 : 부모요소

감싸진(안쪽) 태그 : 자식요소

👉 **Why Indent?**

코드를 보기 좋게 만들어 유지 보수 및 협업에 도움이 된다



### 🌐 글자와 상자

👉 요소가 화면에 출력되는 특성 : **인라인 vs 블록 요소**

- 인라인 : 글자를 만들기 위한 요소들
  - 대표 : `<span>`태그
  - 포함한 **콘텐츠의 크기**만큼 자동으로 **줄어듦**!
- 블록 : 상자(레이아웃)를 만들기 위한 요소들
  - 대표 : `<div>`태그
  - **부모요소의 크기**만큼 자동으로 **늘어남**!

⚠️ **인라인 요소 안에는 블록 요소를 사용할 수 없음**







# 🗓️220829

### 🌐 HTML 핵심요소

👉 블록요소

- `<div>` : Division 태그로 특별한 의미 없이 블록을 구분지을 때 사용

- `<h1>~<h6>` : 컨텐츠의 제목을 나타내는 요소

  → 숫자가 작을수록 더 중요한 제목을 의미함

- `<p>` : paragraph, 문장을 의미하는 요소

- `<ul>` : 순서가 필요없는 목록의 집합(unordered list)

  → 자식요소로 <li>태그를 가진다

  ```html
  <ul>
  	<li>사과</li>
  	<li>딸기</li>
  
  <!--항목은 <li>태그 내용에 나타난다-->
  ```

👉 인라인 요소

- `<img>` : 이미지를 삽입하는 요소

  - 필수 속성 : src(삽입 경로), alt(대체 텍스트)

- `<a>` : anchor, 다른/같은 페이지로 이동하는 하이퍼링크를 지정하는 요소

  → target 속성을 통해 링크의 표시(브라우저 탭) 위치를 설정할 수 있음

- `<span>` : 특별한 의미가 없는 인라인 구분을 위한 요소

  → css를 통해 span 영역만큼의 스타일을 지정한다

⚠️ 인라인-블록 요소

: 글자 요소이지만, 블록 요소의 특징도 가지고 있음

- `input` : 사용자가 데이터를 입력하는 요소
  - 속성 : type, value(미리 입력된 데이터), placeholder(입력할 값의 힌트), disabled(인풋 창 비활성화),
  - type 속성의 종류 : text, checkbox, radio

👉 테이블 요소

- `<table>` : 표 출력

  - `<tr>` table row

  - `<td>` table data

    

### 🌐 주석

👉 단축키 : **ctrl + /**



### 🌐 CSS 기본 문법

👉 `선택자 {속성 : 값;}`

→ 이와 같은 형태로 원하는 부분에 스타일을 지정한다

→ example.

```css
div {
	color : red;
	margin : 20px;
}
```



### 🌐 CSS 선언 방식

👉 내장 방식 : HTML `<style>` 태그 안에 내용으로 작성

```html
<head>
	<style>
		div {
			color: red;
		}
	</style>
</head>
```

👉 **인라인 방식** : 요소의 style 속성에 직접 스타일을 작성

```html
<div style="color: red; margin: 20px;">
</div>
```

→ 인라인 방식의 경우 스타일 지정 우선순위가 너무 높기 때문에 유지 보수 측면에서 권장하지 않음

👉 **링크 방식 :** `<link>`태그로 외부 CSS 문서를 가져와 연결

```html
<link rel="stylesheet" href="./css/main.css">
```

👉 **@import 방식** : CSS의 import 규칙으로 CSS 문서 안에서 또 다른 CSS 문서를 가져와 연결

```css
@import url("./box.css")

div {
	color: red;
	margin: 20px;
}

.box {
	background-color: red;
	padding: 20px;
}
```

*⚠️ 직렬연결 : main.css 없이 box.css가 html 문서에 적용될 수 없음 (연결이 지연된다는 단점이 있음)*



### 🌐 선택자(Selector)

1️⃣ **기본선택자**

- `*` 전체 선택자 : **모든** 요소를 선택

- `ABC` 태그 선택자 : 태그 이름이 ABC인 요소를 선택

  ```css
  li {
  	 color : red;
  }
  ```

- `.ABC` **클래스 선택자** : class 속성의 값이 ABC인 요소 선택

  ```html
  <div class="orange">
  	오렌지
  </div>
  ```

  ```css
  .orange {
  	color : red;
  }
  ```

- `#ABC` **아이디 선택자** : id 속성의 값이 ABC인 요소 선택

  ```html
  <div id="orange">
  	오렌지
  </div>
  ```

  ```css
  #orange {
  	color : red;
  }
  ```

2️⃣ **복합선택자**

- 일치 선택자 : 선택자 ABC와 XYZ를 동시에 만족하는 요소 선택

  ```css
  span.orange {
  	color : red;
  }
  ```

- **자식 선택자** : 선택자 ABC의 자식요소 XYZ 선택

  ```css
  ul > .orange {
  	color : red;
  }
  ```

- **하위 선택자** : 선택자 ABC의 **하위**요소 XYZ 선택

  → ‘띄어쓰기’가 선택자의 기호!!

  ```css
  div .orange{
  	color: red;
  }
  ```

- **인접 형제 선택자** : 선택자 ABC의 **다음 형제 요소** XYZ **하나**를 선택

  ```css
  .orange + li {
  	color: red;
  }
  ```

- 일반 형제 선택자 : 선택자 ABC의 다음형제 요소 XYZ를 **모두** 선택

  ```css
  .orange ~ li {
  	color: red;
  }
  ```

3️⃣ **가상 클래스 선택자**

: 어떤 동작을 했을 때 css만으로 변화를 일으킬 수 있음

```css
.box {
	width: 100px;
	height: 100px;
	background-color: orange;
	transition: 1s;
}

.box:hover {
	width: 300px;
}
```

- `hover` : 선택자 ABC요소에 마우스 **커서가 올라가있는 동안** 선택

- `active` : 선택자 ABC요소에 마우스를 **클릭하고있는**동안 선택

- `focus` : 선택자 ABC요소가 **포커스되면** 선택

  → 포커스가 적용되는 선택자에 적용 가능

  ex ) input 요소