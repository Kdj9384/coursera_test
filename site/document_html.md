<p></p>
<br>:개행
<hr>:줄
space rule
self-closing tag
<head></head>: 메인 컨텐츠에 대한 메타 데이터
charset="utf-8"
<div> : 앞, 뒤를 개행(block 단위)
<span> : 개행하지 않음(구문 단위)
span이 div를 포함할 수 없음

- semantic -
<nav>: 내비게이션
<h1>
<section>
  <article>
<aside>
<footer>

- list -
<ul></ul> : unordered-list
<ol></ol> : ordered-list
<li> : list content
only <li>>tag permitted

- character entity regerences -
3 characters should always escape
'<' -> &lt;
'>' -> &gt;
'&' -> &amp;
&copy; 저작권 표시
&nbsp; 공백을 이 표기로 채우면 문자들을 붙어잇게 할 수 있다.
&quot;

- links(hypertext) -
<a href="URL" title="NAME">표시되는 글(하이퍼링크로)</a> - a태그 : 인라인 태그/블록 태그 둘다 가능
target="_blank" -> 새 탭
<a href="#section"></a> -> id를 이용해 원해는 섹션으로 이동시킬 수 있다.(페이지 내부 이동)(내비게이션)

- displaying images -
<!-- --> : 주석
<img src="URL" width="" height="" alt="추가설명 for 시각장애인"/> - img링크는 인라인 태그이다.
URL은 외부(인터넷이 있는)를 이용할 수 있다.
너비와 높이를 주어질 경우 로딩과정에서 시각적으로 이미지가 어디에서 로딩하는지 알려줄 수 있다. + 이미지 URL이 잘못된 경우 시각적
레이아웃이나 웹페이지의 형태를 의도한대로 유지할 수 잇다.-중요
크롬 개발자 툴 - 네트워크 - 쓸로틀링을 조절해 인터넷 속도를 조절할 수 있다.

<module 2>
- CSS rules
p {
  color: blue;
  font-size: 20px;
  width: 200px;
}
stylesheet -> collection of css rules

- selectors
p -> element selector : 같은 속성을 갖는 태그에 적용
.ClassName -> class selector : 같은 클래스를 가지는 태그에 적용(<p class="ClassName"></p>)
#IdName -> ID selector : 해당 아이디를 가지는 태그에만 적용(하나의 태그) (<p id="IDName"></p>)
div, .blue {
  css설정을 그룹,공유 여러 셀렉터에 동시에 적용가능
}

- combining selector
p.big : p태그 중 big클래스를 갖는 태그 대상
article > p :article태그의 직접 자식인(안에 있는) p태그에만 영향
article p : article태그의 직접 자식 뿐 아니라 태그 안에있는 모든 p태그가 대상
class="class1 class2": 2개 클래스 적용(공백으로 구분)
.class1.class2: class1,class2 동시에 적용된 태그 대상

- pseudo class selector: 적용할 선택자에 붙여서 사용, combining 가능
:link -> 링크
:visited -> 방문 했을때
:hover -> 올려놓기만 할때
:active -> 클릭후 떼지 않았을때
:nth-child()
a:link {
  처럼 사용
}
header li:nth-child(3) {
header안의 모든li중 3번째
}
header li:nth-child(3):hover {
header안의 모든li중 3번째에 마우스를 올려놓을때 변화를 줄 수 있다.
}

- style placement
각 태그안에 style요소를 이용해 사용(style="") - bad
html안에 style태그를 이용해 css사용 - better
css파일(stylesheet) 
<link rel="stylesheet" href="상대URL">

- conflit resolution
같은 요소에 대해 선언시 늦게 선언된 것이 우선함
각기 다른 요소에 대해 선언시 둘다 적용됨
상속
가장 높은 선택자 복잡성이 우쉬를 가진다
style="" > ID> class,attribute,pseudo-class > number of element
"!important" 를 사용해 무조건 덮어씌울 수 있다(우선)

- style text
font-family
font-style
font-weight
font-size
text-transform
text-align
color

-reletive font size
상대적 폰트 사이즈
폰트를 상대적으로 일관되게 사용하는 것이 좋다.
font-size: 1em -> 현재 폰트 사이즈에서 1배

- Box model
padding, border, margin
padding: content와 border사이
margin: border와 배경 사이
width, height -> content 사이즈 조절
box전체 사이즈조절
box-sizing: border-box; -권장, 상속되지 않음, 패딩이나 보더가 바뀌더라도 지정한 크기를 유지함
selector "*" -> to all element and 브라우저 css를 초기화하는 기능

- margin conflict
top, bottom margin conflict -> merge,큰 값을 따라감
left, right margin conflict -> 두 margin값을 더한값을 사이 margin으로 가진다.

- content overflow
default: visible(다 보여주기 위해 넘친다
hidden(보이는 만큼 자른다), auto(스크롤바)

- background property
background-image: url("URL");
background-repeat: no-repeat;
background-position: bottom;
background: url() no-repeat right center ->한번에 지정 가능

- floating
float:  float설정이 되면 기존의 레이아웃(흐름)에서 벗어나 텍스트나 float설정이 된 요소들끼리만 상호작용한다.
clear: float을 취소하는 역할
clear: left = float:left취소

- absolute, relative position
부모가 relative나 absolute요소를 갖고 있어야 자식이 absolute요소를 사용할 수 있다.
부모가 relative요소를 갖는다면
자식이 absolute요소를 부모 안에서 가질 수 있다.
만약, 부모가 relative요소를 갖지 않는다면 relative요소를 갖는 상위태그에 대해 포지셔닝한다.
relative - 기존의 흐름 안에서 
absolute - flow같이 기존의 흐름에서 벗어남, 인식하지 않음

- media queries
@media (조건)[and/or (조건)] {
조건이 참이면 실행
}
(min-width:500px) -> 최소 너비가 500이면 실행된다.

- responsive design



