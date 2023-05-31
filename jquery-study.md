# 4. JQuery
### ****JQuery 로드 순서****

```html
<script src="https://code.jquery.com/jquery-3.3.1.min.js"></script> <!-- JQuery 먼저! -->
<script>
...코드
</script>
```

### 문법

```jsx
$(선택자).동작함수();
```

$() 함수: 선택된 html요소를 jquery에서 이용할 수 있는 형태로 생성해주는 역할

```jsx
window.onload = function() {
    // 자바스크립트 코드
};
$(function() {
   // jQuery 코드
});
```

ready(): 문서가 모두 로드된 뒤에 코드가 실행되도록 설정하는 함수

### ****선택자 & css 스타일 변경하기****

```jsx
$(".클래스") // 선택자 -> css와 동일
$(".클래스").css({"color" : "red"}); // 속성 -> {} 오브젝트안에 css와 동일하게 작성
```

### getter & setter

| 메소드 | 설명 |
| --- | --- |
| .html() | 해당 요소의 HTML 콘텐츠를 반환하거나 설정한다. |
| .text() | 해당 요소의 텍스트 콘텐츠를 반환하거나 설정한다. |
| .width() | 선택한 요소 중에서 첫 번째 요소의 너비를 픽셀 단위의 정수로 반환하거나 설정한다. |
| .height() | 선택한 요소 중에서 첫 번째 요소의 높이를 픽셀 단위의 정수로 반환하거나 설정한다. |
| .attr() | 해당 요소의 명시된 속성의 속성값을 반환하거나 설정한다. |
| .position() | 선택한 요소 중에서 첫 번째 요소에 대해 특정 위치에 존재하는 객체를 반환한다. (getter 메소드) |
| .val() | <form>요소의 값을 반환하거나 설정한다. |

### 메소드 체이닝

```jsx
$("ul").find("li").eq(1).append(" - 추천 메뉴입니다.");

$("ul").find("li").eq(1).append(" - 추천 메뉴입니다.")
	.end().eq(2).append(" - 추천 메뉴입니다.");
```

## ****이벤트(event)란?****

> 웹 페이지는 사용자와 수많은 상호작용을 하게 된다.
사용자는 마우스를 움직이거나, 요소를 클릭하거나, 텍스트 박스에 글을 쓰는 등 수많은 종류의 동작(action)을 수행한다.
> 
> 
> 이러한 사용자의 동작들이 모두 이벤트(event)를 발생시킨다.
> 즉, 이벤트가 발생했다는 것은 웹 페이지에서 특정 동작이 발생하여, 웹 브라우저가 그 사실을 알려주는 것을 의미한다.
> 
> [jQuery 입문 | 이벤트 처리 | 이벤트의 개념(event handler, event object) | devkuma](https://www.devkuma.com/docs/jquery/%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%9D%98-%EA%B0%9C%EB%85%90-event-handler-event-object/)
> 

### 이벤트 객체

- `type` : 이벤트 종류
- `pageX` : 브라우저 화면을 기준으로 한 마우스 X 좌표 위치
- `pageY` : 브라우저 화면을 기준으로 한 마우스 Y 좌표 위치
- `preventDefault()` : 기본 이벤트를 제거한다.
- `stopPropagation()` : 이벤트 전달을 제거한다.

```jsx
// 메소드 호출 없음
$("#text1").on("click", function(e){
    $(this).css('color', 'green'); 
});

// preventDefault 메소드 호출
$("#text2").on("click", function(e){
    $(this).css('color', 'green');

    e.preventDefault();
});

// stopPropagation 메소드 호출
$("#text3").on("click", function(e){
    $(this).css('color', 'green');

    e.stopPropagation();
});

// 둘다 호출
$("#text4").on("click", function(e){
    $(this).css('color', 'green');

    e.preventDefault();
    e.stopPropagation();
});

$("div").on("click", function(e){
    $(this).css('background-color', 'yellow');         
});
```

### .ON() & .OFF() & .ONE()

.**********on()**********

1. 선택한 요소에 어떤 타입의 이벤트라도 연결할 수 있다.
2. 하나의 이벤트 핸들러에 여러 개의 이벤트를 동시에 연결할 수 있다.
3. 선택한 요소에 여러 개의 이벤트 핸들러와 여러 개의 이벤트를 같이 연결할 수 있다.
4. 사용자 지정 이벤트(custom event)를 위해 이벤트 핸들러로 데이터를 넘길 수 있다.
5. 차후에 다루게 될 요소를 이벤트에 바인딩할 수 있다.

```jsx
$("p").on("click", function(){
  alert("문장이 클릭되었습니다.");
});

// 다중 바인
$("p").on({ 
  click: function() {
    $("div").append("마우스가 문장을 클릭했습니다.<br>");
  },
  mouseenter: function() {
    $("div").append("마우스가 커서가 문장 위로 들어왔습니다.<br>");
  },
  mouseleave: function() {
    $("div").append("마우스가 커서가 문장을 빠져 나갔습니다.<br>");
  }
});
```

**.off() - 이벤트 바인딩 제거**

```jsx
$("#btn").on("click", function() {
  alert("버튼을 클릭했습니다.");
});
$("#btnBind").on("click", function() {
  $("#btn").on("click").text("버튼 클릭 가능");
});
$("#btnUnbind").on("click", function() {
  $("#btn").off("click").text("버튼 클릭 불가능");
});
```

**.one() 바인딩 된 이벤트 핸들러가 한 번만 실행되고나서 실행되지 않음**

```jsx
$("button").one("click", function() {
  $("div").append("이제 클릭이 되지 않습니다.<br>");
});
```

### 요소 추가

| .append() | 선택된 요소의 마지막에 새로운 요소나 콘텐츠를 추가한다. |
| --- | --- |
| .prepend() | 선택된 요소의 첫번째에 새로운 요소나 콘텐츠를 추가한다. |
| .appendTo() | 선택된 요소를 해당 요소의 마지막에 추가한다. |
| .prependTo() | 선택된 요소를 해당 요소의 첫번째에 추가한다. |

```jsx
$("p").on("click", function() {
     $(this).toggleClass("wrap");
});
var data = null;
$("#btnDetach").on("click", function() {
    data = $(".hello").detach(); // class가 "hello"인 요소를 모두 삭제한다.
});
$("#btnRestore").on("click", function() {
    $("p").after(data);  // detach() 메소드로 삭제되었던 모든 요소를 다시 추가한다.
});
```

### 상위 요소 탐색

| .parent() | 선택한 요소의 부모(parent) 요소를 선택한다. |
| --- | --- |
| .parents() | 선택한 요소의 상위(ancestor) 요소를 모두 선택한다. |
| .parentsUntil() | 선택한 요소의 상위 요소 중에서 지정한 선택자에 해당하는 요소 바로 이전까지의 요소를 모두 선택한다. |
| .closest() | 선택한 요소를 포함한 상위 요소 중에서 지정한 선택자에 해당하는 요소 중 가장 첫 번째 요소를 선택한다. |

### 하위 요소 탐색

| .children() | 선택한 요소의 자식(child) 요소를 모두 선택한다. |
| --- | --- |
| .find() | 선택한 요소의 자손(descendant) 요소 중에서 전달받은 선택자에 해당하는 요소를 모두 선택한다. |

### 형제 요소 탐색

| .siblings() | 선택한 요소의 형제(sibling) 요소 중에서 지정한 선택자에 해당하는 요소를 모두 선택한다. |
| --- | --- |
| .next() | 선택한 요소의 바로 다음에 위치한 형제 요소를 선택한다. |
| .nextAll() | 선택한 요소의 다음에 위치한 형제 요소를 모두 선택한다. |
| .nextUntil() | 선택한 요소의 형제 요소 중에서 지정한 선택자에 해당하는 요소 바로 이전까지의 요소를 모두 선택한다. |
| .prev() | 선택한 요소의 바로 이전에 위치한 형제 요소를 선택한다. |
| .prevAll() | 선택한 요소의 이전에 위치한 형제 요소를 모두 선택한다. |
| .prevUntil() | 선택한 요소의 형제 요소 중에서 지정한 선택자에 해당하는 요소 바로 다음까지의 요소를 모두 선택한다. |

### 필터링 메소드

| .first() | 선택한 요소 중에서 첫 번째 요소를 선택함. |
| --- | --- |
| .last() | 선택한 요소 중에서 마지막 요소를 선택함. |
| .eq() | 선택한 요소 중에서 전달받은 인덱스에 해당하는 요소를 선택함. |
| .filter() | 선택한 요소 중에서 전달받은 선택자에 해당하거나, 함수 호출의 결과가 참(true)인 요소를 모두 선택함. |
| .not() | 선택한 요소 중에서 전달받은 선택자에 해당하거나, 함수 호출의 결과가 참(true)인 요소를 제외한 나머지 요소를 모두 선택함. |
| .has() | 선택한 요소 중에서 전달받은 선택자에 해당하는 요소를 자손 요소로 가지고 있는 요소를 모두 선택함. |
| .is() | 선택한 요소 중에서 전달받은 선택자에 해당하는 요소가 하나라도 존재하면 참(true)을 반환함. |
| .map() | 선택한 요소 집합의 각 요소마다 콜백 함수를 실행하고, 그 반환값으로 구성된 jQuery 객체를 반환함. |
| .slice() | 선택한 요소 중에서 전달받은 인덱스 범위에 해당하는 요소만을 선택함. |

### 스크롤 위치

| .scrollLeft() | 선택한 요소 집합의 첫 번째 요소의 수평 스크롤 바의 위치를 얻거나, 선택된 요소의 수평 스크롤 바의 위치를 인수로 전달받은 값으로 설정한다. |
| --- | --- |
| .scrollTop() | 선택한 요소 집합의 첫 번째 요소의 수직 스크롤 바의 위치를 얻거나, 선택된 요소의 수직 스크롤 바의 위치를 인수로 전달받은 값으로 설정한다. |

### 프로퍼티 설정

| .attr() | 선택한 요소 집합의 첫 번째 요소의 지정된 속성(attribute)값을 반환하거나, 선택한 요소의 지정된 속성을 전달받은 값으로 설정한다. |
| --- | --- |
| .prop() | 선택한 요소 집합의 첫 번째 요소의 지정된 프로퍼티(property)값을 반환하거나, 선택한 요소의 지정된 프로퍼티를 전달받은 값으로 설정한다. |
| .removeAttr() | 선택한 요소에서 지정된 속성(attribute)을 제거한다. |
| .removeProp() | 선택한 요소에서 지정된 프로퍼티(property)를 제거한다. |

### 클래스 설정

| .addClass() | 선택된 요소에 인수로 전달받은 클래스를 추가한다. |
| --- | --- |
| .removeClass() | 선택된 요소에서 인수로 전달받은 클래스를 제거한다. |
| .toggleClass() | 선택된 요소에 클래스가 없으면 인수로 전달받은 클래스를 추가하고, 전달받은 클래스가 이미 추가되어 있으면 제거한다. |
| .hasClass() | 인수로 전달받은 값이 선택된 요소의 클래스가 존재하는지 여부를 확인한다. |

## ****이펙트(effect) 효과****

### 표시와 숨김

| .hide() | 선택한 요소를 사라지게 한다. |
| --- | --- |
| .show() | 선택한 요소를 나타나게 한다. |
| .toggle() | 선택한 요소에 .show() 메소드와 .hide() 메소드를 번갈아가며 적용한다. |

```jsx
$("#btnHide").on("click", function() {
  $("div").hide();
});
$("#btnShow").on("click", function() {
  $("div").show();
});
$("#btnHide").on("click", function() {
  $("div").hide(1000);
});
$("#btnShow").on("click", function() {
  $("div").show("fast");
});
$("#btnToggle").on("click", function() {
  $("div").toggle();
});
```

### 페이드 효과

| .fadeIn() | 선택한 요소의 CSS opacity 속성값을 높여가며 요소를 나타지게 함. |
| --- | --- |
| .fadeOut() | 선택한 요소의 CSS opacity 속성값을 높여가며 요소를 사라지게 함. |
| .fadeToggle() | 선택한 요소에 fadeIn() 메소드와 fadeOut() 메소드를 번갈아가며 적용함. |
| .fadeTo() | 페이드 효과에서 사용하는 opacity 속성값을 직접 설정함. |

```jsx
$("#btnFadeOut").on("click", function() {
    $("div").fadeOut();
});
$("#btnFadeIn").on("click", function() {
    $("div").fadeIn();
});
$("#btnFadeOut").on("click", function() {
  $("div").fadeOut(1000);
});
$("#btnFadeIn").on("click", function() {
  $("div").fadeIn("fast");
});
$("#btnFadeToggle").on("click", function() {
  $("div").fadeToggle();
});
$("#btnFadeToggle").on("click", function() {
  $("div").fadeToggle();
});
```

> **fade와 show/hide의 다른 점**
fade: opacity를 줄이다가 display:none; 혹은 그 반대
show/hide: width, height를 줄이다가 display:none; 혹은 그 반대
> 

### 슬라이드 효과

| .slideUp() | 선택한 요소의 CSS height 속성값을 높여가며 사라지게 한다. |
| --- | --- |
| .slideDown() | 선택한 요소의 CSS height 속성값을 낮춰가며 나타나게 한다. |
| .slideToggle() | 선택한 요소에 .slideUp() 메소드와 .slideDown() 메소드를 번갈아가며 적용한다. |

```jsx
$("#divBox1").slideUp(); // 인스를 지정하지 않으면 400(0.4초) 동안 올라가면서 사라진다.
$("#divBox2").slideUp(500); // id가 "divBox2"인 요소를 0.5초 동안 올라가면서 사라지게 한다.
$("#divBox1").slideDown(); // 인스를 지정하지 않으면 0.4초(400) 동안 내려오면서 나타나게 한다.
$("#divBox2").slideDown(500); // id가 "divBox2"인 요소를 0.5초 동안 내려오면서 나타나게 한다.

$("#divBox1").slideToggle(); 
$("#divBox2").slideToggle(500); // id가 "divBox2"인 요소를 0.5초 동안 올라가면서 사라지거나 내려오면서 나타나게 한다.
$("#divBox3").slideToggle("fast"); // id가 "divBox3"인 요소를 빠르게 올라가면서 사라지거나 내려오면서 나타나게 한다.
```