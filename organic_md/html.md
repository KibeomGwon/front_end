# HTML
+ 태그<>를 다는 것을 markup이라고 한다.
<br>
+ 여는 태그에서 HTML속성을 설정할 수 있다. <br> ex) <여는 태그 (속성) (속성)>내용</닫는 태그>
+ 주석은 commend+/로 쉽게 생성할 수 있다.<br> 주석을 남용하면 안된다. 브라우저가 주석을 다 가져오기 때문에 사용에 유의를 해야한다.
+ Boilerplate: 언어 혹은 프레임워크 마다 반복적으로 사용되는 구성들


# HTML의 요소: Block + InLine

## Block Element
### block요소들은 브라우저의 넓이 만큼 넓이를 차지한다.
+ h1 ~ h6 태그
<br> 
h 태그(heading)는 글씨를 키우려는 목적으로 사용 X
+ p 태그 (paragraph)
<br>
+ ol (ordered line),ul (unorderd line) 태그 
+ li (list line) 태그
+ div 태그
<br>
여러가지 요소를 모아서 그룹화하는 태그
<br>
class 속성을 많이 활용한다.

## InLine Element
### 특정 Text의 영역에만 영향을 미침
+ a (anchor) 태그
+ span 태그
<br>
텍스트의 일부 영역을 선택할 수 있는 태그 
<br>
div태그와 더불어 class 속성을 많이 활용한다.

<hr>

### og tag
+ og 태그는 웹 페이지의 간략보기를 하게 해주는 프로토콜이다.<br> : 미리보기
+ head태그에서 meta태그로 작성을 한다
+ 속성은 title, description, image가 있다.

<hr>

### 레이아웃
#### header, nav, section, footer
+ 용도별 태그는 영역 분할 뿐만 아니라 기계의 웹 페이지 해석을 도움.
+ semantic: 의미가 잘 전달되는 웹

<hr>

## Github Pages 배포
+ Step 1: 원격 저장소 만들기<br>
'계정명.github.io'라는 이름으로 repository만들기
+ Step 2: 새로운 폴더에 HTML 파일 만들기
+ 첫 html파일의 명은 index.html로 해야한다.
+ repository 명이 html의 주소이다.
