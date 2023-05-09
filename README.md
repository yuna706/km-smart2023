- [수업 정보](#수업-정보)
  * [수업 시간](#수업-시간)
  * [강사 정보](#강사-정보)
  * [목표](#목표)
- [프론트(맛보기)](#프론트맛보기)
  * [1. HTML5 **(Hyper Text Markup Language)**](#1-html5-hyper-text-markup-language)
  * [2. CSS3 ****(Cascading Style Sheet)****](#2-css3-cascading-style-sheet)
  * [3. JS](#3-js)
    + [var, let, const의 차이점](#var-let-const의-차이점)
    + [AJAX 개념](#ajax-개념)
    + [form과 다른 점](#form과-다른-점)
  * [(참고)MVC 패턴](#참고mvc-패턴)
- [JAVA](#java)
  * [자료형](#자료형)
  * [객체지향 프로그래밍](#객체지향-프로그래밍)
    + [class란?](#class란)
    + [Interface 핵심 개념](#interface-핵심-개념)
    + [추상 클래스](#추상-클래스)
    + [Interface ≠ 추상 클래스](#interface-≠-추상-클래스)
    + [사용 목적](#사용-목적)
    + [다형성](#다형성)
    + [필드의 다형성](#필드의-다형성)
    + [매개변수의 다형성](#매개변수의-다형성)
    + [접근 제한자](#접근-제한자)
- [JSP&SERVLET](#jspservlet)
    + [톰캣 설치](#톰캣-설치)
    + [이클립스 환경 세팅](#이클립스-환경-세팅)

<br><br><br><br>
# 수업 정보

## 수업 시간

일시: 매주 토요일 

시간: 12:30 ~ 17:30 총 5시간 수업

수업 시간: 45분 수업 후 15분 쉬는 시간

## 강사 정보

이름: 이유나

연락처: 010-6439-6017

e-mail: yuna706lee@gmail.com

## 목표

1. **HTML5, CSS3, javascript를 이용하여 자기소개 페이지를 퍼블리싱 할 수 있다.**
2. **java의 기본 문법을 파악하여 코드를 작성할 수 있다.**
3. **JSP를 이용하여 동적 웹 페이지를 제작할 수 있다.**
4. **spring boot를 이용하여 웹 애플리케이션 서버를 구동시킬 수 있다.**
5. **git, github를 이용하여 형상관리&협업을 할 수 있다.**

<br>

<br>

# 프론트(맛보기)

- **visual studio code 설치하기**
- **live server 플러그인 설치**
    
    ![Untitled](/readmeImg/1.vs.png)
    

## 1. HTML5 **(Hyper Text Markup Language)**

1. HTML이란 **→ 웹 문서의 구조를 정의하고 콘텐츠를 표현 하는 기본 마크업 언어.**
    - Hyper Text: (다른 텍스트에 대한) 링크가 포함된 텍스트.
    - Markup Language: 텍스트에 의미를 부여하기 위해 문서에 주석을 다는 시스템.
        - xml이란 →  html보다 범용적으로 사용할 수 있는 마크업 언어(사용자 정의)
        - 정보의 앞뒤에 태그(tag)라는 표기를 달아 정보에 의미를 부여하는 형식
    - 크롬과 같은 웹 브라우저는 서버로부터 전달 받은 HTML 문서의 구조를 해석해 화면을 구성함
2. HTML 요소
    
    ![Untitled](/readmeImg/2.html.png)
    
    - 태그: `<>` 를 이용하여 나타냄. 시작과 끝을 표시하는 2개의 쌍으로 이루어지며 종료 태그에는 `</>`를 붙임.
        - 모든 태그가 종료 태그를 가지는 것은 아님.
        - 태그 이름은 대소문자를 구분하지 않음.
        - 태그에 추가적인 정보 부여는 속성을 사용.
    - 속성: 태그에 추가 정보를 제공하기 위해 사용
    - 내용: 시작 태그와 종료 태그 사이에 있는 내용
    - 시맨틱 태그: 특별한 의미를 가지는 태그
        - 화면 디자인에도 영향을 미치지 않지만 코드의 가독성을 높이는 데 도움을 줌
        ex) `<header>, <footer>, <article>, <section>, <aside>, <nav>`
        - 문서의 구조를 정의하기 위하여 다른 태그를 묶는 용도로 사용하는 태그를 컨테이너라고 함.
        - 공간을 구분하는 `<div>` 태그는 단순히 영역을 구분하며 의미를 포함하지 않아 시맨틱 태그와는 구분됨.
3. HTML 구조: DOM(Document Object Model) 구조로 겹겹이 쌓여있는 구조
    
    ```html
    <!DOCTYPE html>
    <html lang="ko">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title>Document</title>
    </head>
    <body>
        contents
    </body>
    </html>
    ```
    
    1. `<!DOCTYPE html>`: HTML5 문서를 선언하는 구문
    2. `<html lang="ko">~</html>`: HTML 문서의 시작과 끝
    3. `<head>~</head>`: css, js, meta, title 태그 등이 위치함
    4. `<body>~</body>`: 문서 본문에 해당하는 부분, 실제 화면에 나타나는 메인 부분
    - `meta`: 화면에 보이지는 않지만 여러 정보를 표현함
4. HTML의 기본 태그
    1. **제목 태그:** `<h1>~<h6>` 까지 있으며 숫자가 작을수록 큰 글자로 출력. 문서에서 제목으로 사용될 텍스트에 사용함.
    * SEO(search engine optimization): 검색엔진에서 html 문서의 내용이 잘 검색될 수 있도록 최적화하는 작업
    2. **문단 태그:** html에서는 연속된 공백이나 줄 바꿈은 단순한 공백으로 처리
    → 문단을 바꿀 때는 `<p>`, 줄을 바꿀 때는 `<br>`, 여러공백은 `&nbsp; or css`
    3. **목록 태그**
        - `<ul>`**:** 순서가 없는 목록
        - `<ol>`**:** 순서가 있는 목록
        - `<li>`: 리스트 아이템
    4. **블록 태그와 인라인 태그**
        - 블록 태그: 라인 전체를 사용하는 태그
            - p, div, h, ul, ol, li 등등
        - 인라인 태그: 해당 요소의 내용만큼만 크기를 갖는 태그
            - span, img, a 등등
        - 인라인 블록 태그: 블록 태그 같이 크기 지정이 가능하며 인라인 태그같이 한 줄에 나란히 배치됨
            - button, input, select 등등
    5. **하이퍼링크 태그**
        
        ```html
        <a href="url" target="window option">링크 텍스트</a>
        ```
        
        - **target 속성 값**
            - `_blank` 새로운 웹 브라우저 창으로 오픈.
            - `_self` 현재 웹 브라우저 창으로 오픈. (기본값)
            - `_parent` 부모 웹 브라우저 창으로 오픈.
            - `_top` 웹 브라우저 전체 영역에 오픈.
        - **책갈피 기능**
            - `<a>`태그를 이용해 같은 문서 내에서 특정 위치로 이동하는 책갈피 기능을 구현할 수 있음.
            - `<p>`태그의 `name`속성이나 `id`속성을 이용해 문서 내 이동위치를 지정하고 하이퍼링크에 `href=#name(id)` 과 같이 이동할 위치를 지정함.
    6. **form과 input 태그**
        
        ```html
        <form action="/submit.html" method="get">
            이름 : <input type="text" name="name"><br>
            아이디 : <input type="text" name="id"><br>
            비밀번호 : <input type="password" name="password"><br>
            <input type="submit">
        </form>
        ```
        
        - **form**: 데이터를 전송하기 위한 구조
        - **form** 주요 속성
            
            ![Untitled](/readmeImg/3.html.png)
            
        - **input:** 사용자로부터 입력을 받을 수 있는 입력 필드를 정의할 때 사용
            - 종류: text, number, email, password, file, date, radio, checkbox 등
        - **input** 주요 속성 - [코딩의 시작, TCP School](http://www.tcpschool.com/html-tags/input)

## 2. CSS3 ****(Cascading Style Sheet)****

1. css란 → html과 함께 웹을 구성함. 글씨의 색상이나 크기 같은 웹 문서의 디자인 요소
2. 장점
    1. 웹 문서의 내용과 별개로 디자인만 바꾸거나 디자인은 그대로 두고 웹 문서의 내용 변경이 용이함
    2. 해상도에 따른 반응형 디자인을 구현할 수 있음(미디어 쿼리)
    3. 동일한 문서 구조이더라도 서로 다른 CSS 테마 적용이 가능함
3. 동작 원리
    
    ```css
    #test {
    	style : ~~;
    }
    ```
    
    1. 선택자: HTML 문서에서 디자인 적용을 원하는 요소를 선택함
    2. 선언부: 적용하고자 하는 디자인 속성을 선언함
4. 스타일 적용 방법
    1. 인라인 스타일 시트: HTML 태그에 css 속성을 정의
    2. 내장 스타일 시트: html 문서의 head부분에 작성. 현재 작성한 문서에만 적용됨
    3. 외장 스타일 시트: 별도의 css 파일을 생성하여 html 문서에 링크로 포함. 하나의 파일로 여러 문서에 적용 가능
5. 선택자 종류
    1. 전체 선택자: `* {~}` ⇒ 전역 초기화할 때 사용
    - 태그 선택자 : 해당 태그를 사용하는 노드를 전체 선택
        
        ```html
        <div> <!-- 부모 태그 -->
        	<p></p>
        	<p></p>
        	<p>
        		<a href="naver.com">네이버로 이동</a> <!-- 최하위 자식 태그 -->
        	</p>
        </div>
        ```
        
        ```css
        p {
        	style : ~~
        }
        ```
        
        ```jsx
        // 1
        document.getElementsByTagName('p');
        
        //2
        $("p")
        ```
        
    - class 선택자 : 중복 가능
        
        ```jsx
        <div class="test"></div>
        ```
        
        ```css
        .test {
        	style : ~~
        }
        ```
        
        ```jsx
        // 1
        document.getElementByClassName('test');
        
        //2
        $(".test")
        ```
        
    - id 선택자 : 중복 불가
        
        ```jsx
        <div id="test"></div>
        ```
        
        ```css
        #test {
        	style : ~~
        }
        ```
        
        ```jsx
        // 1
        document.getElementById('test');
        
        //2
        $("#test")
        ```
        
    - 복합 선택자
        
        ```html
        <div> <!-- 부모 태그 -->
        	<p></p>
        	<p></p>
        	<p class="test">
        		<a href="naver.com">네이버로 이동</a> <!-- 최하위 자식 태그 -->
        	</p>
        </div>
        ```
        
        ```css
        div> p> a {
        	style : ~~
        }
        
        p.text> a {
        	style : ~~
        }
        ```
        
        ```jsx
        // 1
        document.querySelector('p.text> a');
        
        //2
        $("p.text> a")
        ```
        
    - 속성 선택자
        
        ```html
        <div> <!-- 부모 태그 -->
        	<p></p>
        	<p></p>
        	<p name="test">
        		<a href="naver.com">네이버로 이동</a> <!-- 최하위 자식 태그 -->
        	</p>
        </div>
        ```
        
        ```css
        a[href="naver.com"] {
        	style : ~~
        }
        p[name="test"]{
        	style : ~~
        }
        ```
        
        ```jsx
        // 1
        document.querySelector('p.text> a');
        
        //2
        $("p.text> a")
        ```
        
    - 가상 클래스 선택자
        
        ```html
        <div> <!-- 부모 태그 -->
        	<p></p>
        	<p></p>
        	<p name="test">
        		<a href="naver.com">네이버로 이동</a> <!-- 최하위 자식 태그 -->
        	</p>
        </div>
        ```
        
        ```css
        /* n 번째 자식*/
        p:nth-child(3) {
        	style : ~~
        }
        /* 마우스를 올렸을 때*/
        a:hover{
        	style : ~~
        }
        ```
        
        ```jsx
        // 1
        document.querySelector('a').addEventListener("mouseover", function(){
        	[function]
        });
        
        //2
        $("a").hover(function(){
        	[function]
        })
        ```
        
6. 주요 제어 스타일
    1. width, height: 넓이, 높이
    2. display: block, inline, inline-block, grid, flex
    3. position: absolute, fixed, relative, sticky
        - top, right, bottom, left
    4. border, padding, margin: 여백
        - border: 테두리 - [코딩의 시작, TCP School](http://www.tcpschool.com/css/css_boxmodel_borders)
        - padding: 내용과 테두리의 간격
        - margin: 테두리와 이웃하는 요소 사이의 간격
    5. font-size, font-style, color: 글자 서식
    6. background: 요소의 배경
        - img, color, position, size 등등
---
## ※퍼블리싱 실습※
1. 자기 소개 페이지 만들어보기
2. 카카오뉴스 클론코딩하기 - [https://www.kakaocorp.com/page/news?tab=all](https://www.kakaocorp.com/page/news?tab=all)

---
## 3. JS
[https://developer.mozilla.org/ko/](https://developer.mozilla.org/ko/)

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>js 놀기</title>
</head>
<body>
    <button onclick="getMenu()">메뉴를 주세요!</button>
</body>
</html>
```

```jsx
// menu는 전역 변수 = 어디서든 접근이 가능함
// const 는 상수형으로 변경이 불가능
const menu = ["중국집", "서브웨이", "분식", "초밥", "피자"];

function getRandomInt(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min)) + min; //최댓값은 제외, 최솟값은 포함
}

function getMenu(){
    let min = 0; //함수내에서만 사용이 가능한 지역 변수
    let max = menu.length - 1;
    let randVal = getRandomInt(min, max);
    let p = document.createElement("p");
    p.textContent = menu[randVal];
    document.body.appendChild(p);
}
```

### var, let, const의 차이점

- var : 재선언, 재할당 가능
- let : 재선언 불가능, 재할당 가능
- const : 상수형 - 재선언, 재할당 불가능
- var가 재선언이 가능한 이유
    - **호이스팅이란** 변수 선언문, function 선언문 등을 해당 스코프의 선두로 옮긴 것처럼 동작하는 특성
    - 변수는 `선언 단계` > `초기화 단계` > `할당 단계` 에 걸쳐 생성되는데 `var`로 선언된 변수는 선언 단계와 초기화 단계가 한번에 이루어짐
        
        `let` 로 선언된 변수는 선언 단계와 초기화 단계가 분리되어 진행됨
        
        ```jsx
        // 스코프의 선두에서 선언 단계와 초기화 단계가 실행된다.
        // 따라서 변수 선언문 이전에 변수를 참조할 수 있다.
        
        console.log(foo); // undefined
        
        var foo;
        console.log(foo); // undefined
        
        foo = 1; // 할당문에서 할당 단계가 실행된다.
        console.log(foo); // 1
        ```
        
        ```jsx
        // 스코프의 선두에서 선언 단계가 실행된다.
        // 아직 변수가 초기화(메모리 공간 확보와 undefined로 초기화)되지 않았다.
        // 따라서 변수 선언문 이전에 변수를 참조할 수 없다.
        
        console.log(foo); // ReferenceError: foo is not defined
        
        let foo; // 변수 선언문에서 초기화 단계가 실행된다.
        console.log(foo); // undefined
        
        foo = 1; // 할당문에서 할당 단계가 실행된다.
        console.log(foo); // 1
        ```
        
    
    참고 자료: [var, let, const 차이점 (velog.io)](https://velog.io/@bathingape/JavaScript-var-let-const-%EC%B0%A8%EC%9D%B4%EC%A0%90)
    

### AJAX 개념

**AJAX란?** 서버와 통신하기 위해 **`XMLHttpRequest`** 객체를 사용하는 것

**특징**

- 페이지 새로고침 없이 서버에 요청 - **비동기성**
- 서버로부터 데이터를 받고 작업을 수행

### form과 다른 점

<aside>
💡 **form(동기식) :** action 속성에 지정한 url로 데이터를 전송하며 **응답 데이터로 이동 및 표출**

**ajax(비동기식):** 지정한 url로 데이터를 전송하여 **응답 값을 데이터 객체**로 받아와 js에서 가공이 가능함

</aside>

참고 자료: [Ajax 시작하기 - 웹 개발자 안내서 | MDN (mozilla.org)](https://developer.mozilla.org/ko/docs/Web/Guide/AJAX/Getting_Started)

## (참고)MVC 패턴

MVC: Model, View, Controller의 약자

- model: 데이터 객체
- view: 데이터 및 객체의 입출력 ⇒ 사용자가 볼 수 있는 영역
- controller: 데이터 처리 부분, 데이터 가공 및 요청&응답

참고하면 좋을 자료 - [https://m.blog.naver.com/jhc9639/220967034588](https://m.blog.naver.com/jhc9639/220967034588)

**spring mvc 패턴**

- model = VO or DTO
- view = jsp
- controller = service, controller, DAO

<br>

<br>

# JAVA

## 자료형

- [03장 자료형 - 점프 투 자바 (wikidocs.net)](https://wikidocs.net/192)
- [03장 연습문제 - 점프 투 자바 (wikidocs.net)](https://wikidocs.net/157658)

```jsx
a = a == 3 ? “남자” : “여자”;
if(a == 3)
	a = "남자";
else
 a = "여자"
```

## 객체지향 프로그래밍

### class란?

- **객체 지향 프로그래밍(OOP, Object-Oriented Programming)**은 모든 데이터를 객체(object)로 취급
- **클래스(class)**란 객체를 정의하는 틀 또는 설계도와 같은 의미
    
    ![[05-02 클래스 - 점프 투 자바 (wikidocs.net)](https://wikidocs.net/214)](/readmeImg/4.java.png)
    
    [05-02 클래스 - 점프 투 자바 (wikidocs.net)](https://wikidocs.net/214)
    
- **객체(Object)와 인스턴스(Instance)**
    
    클래스를 사용하기 위해서는 해당 클래스 타입의 객체(object)를 선언해야 합니다.
    
    이렇게 클래스로부터 객체를 선언하는 과정을 클래스의 인스턴스 화라고 합니다.
    
    또한, 이렇게 선언된 해당 클래스 타입의 객체를 인스턴스(instance)라고 합니다.
    
    즉, 인스턴스란 메모리에 할당된 객체를 의미합니다.
    
    자바에서는 하나의 클래스로부터 여러 개의 인스턴스를 생성할 수 있습니다.
    
    이렇게 생성된 인스턴스는 독립된 메모리 공간에 저장된 자신만의 필드를 가질 수 있습니다.
    
    하지만 해당 클래스의 모든 메소드(method)는 해당 클래스에서 생성된 모든 인스턴스가 공유하게 됩니다.
    

```java
class MyObject{
    private int index;
    MyObject(int index) {
        this.index = index;
    }
    public int getIndex() {
        return index;
    }
    public void setIndex(int index) {
        this.index = index;
    }
}
public class ClassType {
    public static void main(String[] args) {
        MyObject a = new MyObject(2);
        MyObject b = new MyObject(4);
        System.out.println(a.getIndex()); // "a" result is 2.
        a = b;
        System.out.println(a.getIndex()); // "a" result is 4.
        b.setIndex(6);
        System.out.println(a.getIndex()); // "a" result is 6.
    }
}
```

### Interface 핵심 개념

- **인터페이스의 특성**
    1. 변수, 메서드의 **껍데기**만 있음
    2. 클래스를 선언할 때 `implements` 를 이용해 구현함
    3. 다중 상속이 가능함
    4. **인터페이스에 선언된 구조체는 모두 구현하도록 강제함**

- **인터페이스를 사용하는 이유**
    1. 클래스를 파라미터로 받는 메소드가 있을 때, 클래스마다 다른 실행을 하기 위해 오버로딩(overloading)을 해야 함
    → 즉, 새로운 클래스가 생성될 때마다 오버로딩 메소드는 추가되어야 함
        
        ```java
        class ZooKeeper {
            void feed(Tiger tiger) {  // 호랑이가 오면 사과를 던져 준다.
                System.out.println("feed apple");
            }
        
            void feed(Lion lion) {  // 사자가 오면 바나나를 던져준다.
                System.out.println("feed banana");
            }
        }
        ```
        
    2. 구현체는 메소드의 파라미터는 인터페이스로 받아올 수 있음
    → tiger, lion은 각각 Tiger, Lion의 객체이기도 하지만 Predator 인터페이스의 객체이기도 하기 때문(IS-A 관계 적용)
        
        ```java
        interface Predator {
        		Stirng getFood()~~{}~~;
        		~~int age()~~
        }
        
        class Tiger extends Animal implements Predator {
        		public String getFood() {
                return "apple";
            }
        }
        
        class Lion extends Animal implements Predator {
        		public String getFood() {
                return "banana";
            }
        }
        
        class ZooKeeper {
            void feed(Predator predator) {
                System.out.println("feed "+predator.getFood());
            }
        }
        ```
        
        1. 구현체는 여러개가 될 수 있지만 인터페이스는 하나임
        **→ 파라미터로 받는 클래스에 의존적인 클래스 → 파라미터 클래스와는 상관없는 독립적인 클래스가 됨**

- 디폴트 메서드, 스태틱 메서드 - interface에서 미리 메서드 선언 가능
    
    ```java
    interface Predator {
        String getFood();
    		(public static final) int pie = 3.14;
        default void printFood() {
            System.out.printf("my food is %s\n", getFood());
        }
    
        int LEG_COUNT = 4;  // 인터페이스 상수 - 자동으로 public static fianl 설정됨
    
        static int speed() {
            return LEG_COUNT * 30;
        }
    }
    ```
    

### 추상 클래스

- 추상 클래스는 **인터페이스의 역할&클래스의 기능도 갖고 있는 클래스**
    - 추상 메소드를 작성하기 위해선 추상 클래스임을 선언해야 함
- 클래스의 **상속과 동일하게 구현**하되, **추상 메소드를 생성하여 인터페이스처럼 사용**이 가능함
- 인터페이스와 동일하게 추상 메소드로 선언된 메서드는 반드시 구현되어야 함.
즉, 추상 클래스를 바로 생성할 수 없으며 **구현체 클래스를 생성**해야 함.
- 추상클래스를 상속받은 클래스에서는 구현된 클래스는 구현하지 않아도 됨
* void  printFood(), int speed()는 구현되어 있으므로 구현하지 않음

```jsx
abstract class Predator extends Animal { //추상 클래스 선언
    abstract String getFood(); //추상 메소드 선언
		public static final int LEG_COUNT = 4;  // 추상 클래스의 상수는 static 선언이 필요하다. - static은 아래에서 확인
   
    void printFood() {
        System.out.printf("my food is %s\n", getFood());
    }

    int speed() {
        return LEG_COUNT * 30;
    }
}

class Tiger **extends Predator** implements Barkable {
		@Override // 추상메소드여도 @Override 어노테이션을 붙인다.
		String getFood(){
				(...생략...)
		}
}
```

### Interface ≠ 추상 클래스

|  | interface | 추상 클래스 |
| --- | --- | --- |
| 메소드 | 인터페이스는 구조체이므로 메소드 내용이 없다. | 추상클래스는 일반 클래스처럼 객체 변수, 생성자 등을 가질 수 있다. |
| 변수 | 선언시 자동으로 public static fianl이 붙어 변경이 불가능하다 | 선언시 접근제한자, 정적 여부, 상수 여부를 직접 선언한다. 
→ 일반 클래스에서의 선언과 동일 |
| 상속 | 다중 상속 가능(implements) | 단일 상속(extends) |
| 구현 | 모든 메소드 구현 강제(default, static 제외) | 추상 메소드만 구현 강제(@Override 어노테이션 사용), 이미 구현된 메소드는 자율 |

### 사용 목적

<aside>
💡 추상클래스: 클래스는 상속받아서 기능을 **이용하고 확장** 시킴
인터페이스: 함수의 껍데기만 선언하고 함수의 구현을 강제하여 **구현 객체의 같은 동작을 보장**

</aside>

참고: [자바의 추상 클래스와 인터페이스 (brunch.co.kr)](https://brunch.co.kr/@kd4/6#comment), [[초급 JAVA]자바 interface 와 abstract 예제로 이해하기 (tistory.com)](https://commin.tistory.com/106)

### 다형성

- 다형성(**Polymorphism)**: 하나의 객체가 여러개의 자료형 타입을 가질 수 있는 것
→ **같은 타입이지만 실행 결과가 다양한 결과가 나오는 성질**
- 다형성은 하나의 타입에서 여러 객체를 대입함으로써 다양한 기능을 이용할 수 있도록 해줌.
- 다형성을 위해 자바는 부모 클래스로 타입 변환을 허용함.
- 모든 자식은 부모 객체로 타입 변환할 수 있음.
    - 이것을 응용하면 상위 타입에 대해 다양한 하위 타입을 적용하여 다형성을 이용할 수 있음.
    - 부모 클래스 변수 타입에 자식 클래스 변수를 할당하면 자식에서 부모로 자동으로 타입이 변환됨.
    - 자동 타입 변환된 부모 클래스에서 자식 클래스에 의해 오버라이드된 메소드를 호출하면, 오버라이드된 메소드가 호출됨.
    
    ```java
    class Parent { ... }
    
    class Child extends Parent { ... }
    
    ...
    
    Parent pa = new Parent(); // 허용
    
    Child ch = new Child();   // 허용
    
    Parent pc = new Child();  // 허용
    
    Child cp = new Parent();  // 오류 발생.
    ```
    

### 필드의 다형성

필드의 타입은 변함이 없지만 실행 도중에 어떤 객체를 필드로 저장하느냐에 따라 실행 결과가 달라질 수 있음

예를 들어, 우리가 Tire라는 부모 클래스를 만들었다고 가정해 보자. 그런데 기술이 점점 발전하거나, 기기가 고장이 나서 타이어를 교체해야 하는 상황이 왔다고 하자. 이때, 만약 부모 타입의 클래스를 상속 받은 자식 객체에서, 더 좋은 기능을 장착한 후(오버라이딩), 타이어를 해당 타이어로 업그레이드할 수 있다면 어떨까?

새로 교체되는 타이어 객체는 기존 타이어와 사용 방법은 동일하지만 실행 결과는 더 우수하게 나와야 함.

→ 상속과 오버라이딩, 타입 변환을 이용하여 프로그램으로 구현

* 타이어 프로젝트 실습

### 매개변수의 다형성

- **매개 변수의 타입이 클래스일 경우, 해당 클래스의 객체 뿐만 아니라 자식 객체까지도 매개 값으로 사용할 수 있음**
- 매개 값으로 어떤 자식 객체가 제공 되느냐에 따라 메소드의 실행 결과가 달라짐
⇒ 매개변수의 다형성
→ 자식 객체가 부모의 메소드를 재정의(오버라이딩)했다면 메소드 내부에서 오버라이딩된 메소드를 호출함으로써 메소드의 실행 결과는 다양해짐

### 접근 제한자

![Untitled](/readmeImg/7.java.png)

연습 문제 1, 2, 4, 7, (~~6, 8,~~ 9) - 이야기하기


<br>

<br>


# JSP&SERVLET

1. 동적 페이지, 정적 페이지
    1. **정적 페이지란** html, text와 같이 미리 저장된 정보를 보여주는 페이지로 변화가 없음
    2. **동적 페이지란** 사용자에 따라서 정보를 가공하여 리턴함 ex) 날씨, 뉴스 등
2. JSP란? 
    1. **JSP란** 동적 페이지를 생성하기 위한 프로그래밍 언어
    2. 특징
        1. 서버단에서 동적인 요소를 생성하여 순수 html과 결합해 종합적인 결과를 사용자에게 반환함
        → 사용자는 jsp 코드가 아닌 순수한 html 코드만을 보게 됨
            
            ```tsx
            <%@ page language="java" contentType="text/html; charset=UTF-8"
                pageEncoding="EUC-KR"%>
            <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
            <html>
            <head>
            <meta http-equiv="Content-Type" content="text/html; charset=EUC-KR">
            <title>Insert title here</title>
            </head>
            <body>
            <%
               String strName = "홍길동";
            %>
            내 이름은 <%=strName%> 입니다.
            </body>
            </html>
            ```
            
3. Servlet 이해하기
    1. 서블릿은 자바 코드 안에 HTML 태그들이 포함 되어 있음
        
        ```tsx
        package ch03;
        
        import java.io.*;
        import javax.servlet.*;
        import javax.servlet.http.*;
        import javax.servlet.annotation.WebServlet;
        
        @WebServlet(urlPatterns = "/ch03/myServlet1")
        public class MyServlet1 extends HttpServlet {
        
        	@Override
            public void service(HttpServletRequest request, HttpServletResponse response)
            throws IOException, ServletException{
                response.setContentType("text/html");
                PrintWriter out = response.getWriter();
                out.println("<html>");
                out.println("<head>");
                out.println("<title>MyServlet1</title>");
                out.println("</head>");
                out.println("<body>");
                out.println("<h1>Fighting Korea!!!</h1>");
                out.println("</body>");
                out.println("</html>");
            }
        }
        ```
        
    2. 즉 퍼블리싱을 수정하기 위해 디자이너가 JAVA 코드를 접근해야하고 수정사항이 생길시 새로 빌드해야함
    → 수정에 용이하지 않고 동적인 부분과 정적인 부분을 분리하기 어려움
    3. **서블릿의 특성과 JSP의 특성을 살려서 상호 보완적인 관계로 JSP는 화면 출력 부분을 맡고 서블릿은 처리부분을 맡음**
4. (실습)톰캣 설치, 이클립스 환경 세팅
    
    ### 톰캣 설치
    
    1. [Apache Tomcat® - Apache Tomcat 8 Software Downloads](https://tomcat.apache.org/download-80.cgi)
        
        ![Untitled](/readmeImg/tomcat%20(1).png)
        
    2. 다운로드 후 적당한 위치에 압축해제
        
        
    3. java 버전 확인(1.8)
        
        ![Untitled](/readmeImg/tomcat%20(2).png)
        
    4. /bin/startup.bat 실행 → startup {시간} 확인되면 브라우저(chrome)에 [localhost](http://localhost):8080 접근
        
        ![Untitled](/readmeImg/tomcat%20(3).png)
        ![Untitled](/readmeImg/tomcat%20(4).png)
        
    
    ### 이클립스 환경 세팅
    
    1. 워크스페이스 생성
        
        ![Untitled](/readmeImg/Untitled.png)
        
    2. 톰캣 서버 추가
        
        ![하단 패널에서 server 탭 열기 → 파란 글씨 클릭](/readmeImg/Untitled%20(1).png)
        
        하단 패널에서 server 탭 열기 → 파란 글씨 클릭
        
        ![톰캣 8.5 선택 후 next](/readmeImg/Untitled%20(2).png)
        
        톰캣 8.5 선택 후 next
        
        ![Browse 버튼을 눌러 톰캣 지정 후 Finish](/readmeImg/Untitled%20(3).png)
        
        Browse 버튼을 눌러 톰캣 지정 후 Finish
        
    3. Dynamic Web 프로젝트 생성
        
        ![project explorer 배경에서 우클릭 후 다이나믹 웹 프로젝트 선택](/readmeImg/Untitled%20(4).png)
        
        project explorer 배경에서 우클릭 후 다이나믹 웹 프로젝트 선택
        
        ![project name 입력 후 target runtime에서 아까 설치한 톰캣 선택 후 넥스트](/readmeImg/Untitled%20(5).png)
        
        project name 입력 후 target runtime에서 아까 설치한 톰캣 선택 후 넥스트
        
        ![빈칸으로 된 폴더 아이콘 선택 후 edit](/readmeImg/Untitled%20(6).png)
        
        빈칸으로 된 폴더 아이콘 선택 후 edit
        
        ![src로 경로 지정 후 하단 default output folder 경로 설정](/readmeImg/Untitled%20(7).png)
        
        src로 경로 지정 후 하단 default output folder 경로 설정
        
        ![content directory 폴더명 입력 후 finish](/readmeImg/Untitled%20(8).png)
        
        content directory 폴더명 입력 후 finish
        
    4. jsp 생성
        
        ![프로젝트 명을 좌클릭한 후 우클릭→new→jsp file 선택](/readmeImg/Untitled%20(9).png)
        
        프로젝트 명을 좌클릭한 후 우클릭→new→jsp file 선택
        
        ![WebContent 폴더 선택 후 file name 작성하여 finish](/readmeImg/Untitled%20(10).png)
        
        WebContent 폴더 선택 후 file name 작성하여 finish
        
    5. jsp 빌드 후 브라우저 확인
    
    ![본문 작성 후 run 버튼 클릭](/readmeImg/Untitled%20(11).png)
    
    본문 작성 후 run 버튼 클릭
    
    ![브라우저에서 확인](/readmeImg/Untitled%20(12).png)
    
    브라우저에서 확인
    
5. Servlet이란?
    1. 동적인 웹 콘텐츠를 생성하는 기술로 제공
    → jsp와 동일하게 웹 페이지에서 호출을 하여 실행 결과를 순수 html로 제공함
        1. JSP 동작 구조
            
            ![Untitled](/readmeImg/5.jsp.png)
            
            1. 클라이언트(브라우저)가 도메인으로 요청
            2. 웹 서버에서 요청온 JSP 파일을 파싱
            3. JSP 파일로부터 서블릿이라는 새로운 자바파일 생성
            4. 서블릿 파일이 실행 가능한 상태인 클래스 파일로 컴파일
            5. 클라스 파일의 실행 결과가 웹서버로 넘겨져 HTML  형태로 응답 내용을 리턴
            6. 웹 서버로 받은 HTML을 브라우저(클라이언트)에서 실행
            - 이전에 요청된 적이 있으면 이미 클래스 파일로 변환되었기 떄문에 5번 단계부터 실행됨
6. JSP의 스트립트
    
    ```java
    <%@ page contentType="text/html;charset=EUC-KR"%>
    <html>
    <head><title>JSP스크립트 Example</title></head>
    <body>
      <h1>Script Example1</h1>
     <%!
     	     String declaration = "Declaration";
     %>
     <%!
     	public String decMethod(){
     	
     	 return declaration;
     	}
     %>
     <%
     	String scriptlet = "Scriptlet";
        String comment = "Comment";
    
     	out.println("내장객체를 이용한 출력 : " + declaration + "<p/>");
     %>
    
     선언문의 출력1 : <%=declaration%><p/>
     선언문의 출력2 : <%=decMethod()%><p/>
     스크립트릿의 출력 : <%=scriptlet%><p/>
     <!--JSP주석부분-->
     <!-- JSP 주석1 :  <%=comment%> --><p/>
     <%-- JSP 주석2 : <%=comment%> --%>
     <%  /* 주석 
        (여러줄 주석)
         */  
     %> 
     <%// 주석(한줄 주석)%>
     </body>
     </html>
    ```
    
    1. 선언문(Declaration)
        - 뜻: jsp에서 사용될 변수나 메소드를 선언할 수 있는 영역
        - 문법: `<%! ~ %>`
        - 선언문에서 선언된 변수를 멤버 변수라고 부름(클래스 안에 선언된 변수)
        - 멤버 메소드, 멤버 변수로 선언됨 → 즉, 클래스 생성 시 제일 먼저 실행되어 생김
        - 일반적으로 잘 사용되지 않음
            - 멤버 변수를 사용하는 때는 클래스에서 선언된 여러 메소드에서 공통적으로 사용될 때임
            - 하지만 jsp에서 메소드를 선언하는 일은 거의 없음
            - jsp에서 선언된 메소드는 해당 jsp에서만 사용할 수 있으며 다른 jsp에서 사용할 메소드하면 java 파일을 만들어서 모든 jsp에서 참조하여 사용함
    2. 스크립트릿(Scriptlet)
        - 뜻: jsp 페이지가 서블릿으로 변환되고 요청될 때 _jspService 메소드 안에 선언이 되는 요소
        - 문법: `<% ~ %>`
        - 일반적으로 많이 사용되는 스크립트 요소
        - 선언문과 달리 선언된 변수는 변수로 선언이 되고 메소드 선언을 할 수 없음
            - 선언하게 된다면 메소드 안에 메소드를 선언한 것이므로 만들 수 없음
    3. 표현식
        - 문법: `<%= %>`
        - 표현식의 활용 — for문, 삼항 연산자
7. JSP의 지시자와 액션 태그
    1. 지시자의 종류
        1. page: JSP 컨테이너에게 해당 페이지를 어떻게 처리할 것인가에 대한 페이지 정보를 알려줌
            
            
            | 속성 | 값 | 기본값 | 예제 |
            | --- | --- | --- | --- |
            | info | 텍스트| 없음| info=“Copyright2013 by JspStudy.co.kr”|
            | language| 스크립팅 언어| “java”| language=“java”|
            | contentType| MIME타입, 문자집합| contentType=“text/html charset=ISO-8859-1”| contentType=“text/html; charset=EUC-KR”|
            | extends| 클래스이름| 없음| extends=“kr.co.jspstudy.board.JspPage”|
            | import| 클래스/패키지이름| 없음| import=“java.util.Vector”import=“java.sql.*,java.net.*”|
            | session| boolean값| “true”| session=“true”|
            | buffer| buffer값 or“none”| “8kb”| buffer=“12kb”buffer=“false”|
            | autoFlush| boolean값| “true”| autoFlush=“false”|
            | isThreadSafe| boolean값| “true”| isThreadSafe=“true”|
            | trimDirective Whitespaces| boolean 값| “false”| trimDirectiveWhitespaces=“false”|
            | errorPage| 로컬 URL| 없음| errorPage=“error/fail.jsp”|
            | isErrorPage| boolean값| “false”| isErrorPage=“false”|
            | pageEncoding| 페이지의캐릭터 인코딩값| “ISO-8859-1”| pageEncoding=“EUC-KR”|
        2. include: 여러 JSP 페이지에서 공통적으로 포함하는 내용이 있을 때 따로 저장하여 다른 JSP 파일에 삽입할 수 있도록 함
            
            ```xml
            <%@include file=“로컬URL”%>
            ```
            
        3. taglib: JSP 기능을 확장할 떄 사용하는 사용자 정의 태그의 집합
        → 양이 많아 추후 서술
8. JSP의 내부객체
    - JSP 페이지를 작성할 때 특별한 기능을 제공하는 JSP 컨테이너가 제공하는 특별한 객체
    - JSP에서 선언하지 않고 사용할 수 있는 객체
    - 스크립트 요소에서 내부 객체와 동일한 변수명으로 선언할 수 없다.
    - 사용되는 범주에 따라 4가지 형태로 분류
    - JSP 페이지 입출력 관련 내부 객체
    - JSP 페이지 외부 환경 정보 제공 내부 객체
    - JSP 페이지 서블릿 관련 내부 객체
    - JSP 페이지 예외 관련 기본객체
    - 내부객체 타입과 설명
        
        ![Untitled](/readmeImg/6.jsp.png)
        
9. 세션을 이용한 사용자 정보 제어 실습 
    
    ```html
    <html>
    <head>
    	<meta charset="UTF-8">
    	<title>session</title>
    </head>
    <body>
    	<form method="post" action="session1.jsp">
    		<input name="id" placeholder="아아디"> <br>
    		<input type="password" name="password" placeholder="비밀번호"> <br>
    		
    		<button type="submit">로그인</button>
    	</form>
    </body>
    </html>
    ```
    
    ```html
    <%@ page language="java" contentType="text/html; charset=EUC-KR"
        pageEncoding="UTF-8"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>session1</title>
    </head>
    <body>
    	<%
    		request.setCharacterEncoding("UTF-8");
    
    		String id = request.getParameter("id");
    		String pwd = request.getParameter("password");
    		
    		session.setAttribute("idKey", id);
    		session.setMaxInactiveInterval(10);
    	%>
    
    	<form method="post" action="session2.jsp">
    		<input name="name" placeholder="이름"> <br>
    		<input name="age" placeholder="나이"> <br>
    		
    		<button type="submit">전송</button>
    	</form>
    </body>
    </html>
    ```
    
    ```html
    <%@ page language="java" contentType="text/html; charset=EUC-KR"
    	pageEncoding="UTF-8"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>session 2</title>
    </head>
    <body>
    	<%
    		String name = request.getParameter("name");
    		String age = request.getParameter("age");
    		String id = (String) session.getAttribute("idKey");
    		String sessionId = session.getId();
    		int intervalTime = session.getMaxInactiveInterval();
    		
    		if(id != null && !id.isEmpty()){
    	%>
    			이름: <%=name%> <br>
    			세션 id: <%=sessionId%> <br>
    			세션 유지 시간: <%=intervalTime%>초 <br>
    	<%	
    			session.invalidate();
    		}else{
    	%>
    			<h1>세션이 종료되었습니다.</h1>
    	<%	
    		}
    	%>
    </body>
    </html>
    ```
