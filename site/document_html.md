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
