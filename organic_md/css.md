# CSS
+ css를 html과 연결하는 방법은 헤드태크 안에 link태그를 이용하여 연결한다.

### Box-Sizing
+ 박스에 적용된 사이즈의 기준 정하기
<br> 
box-sizing:content-box; => 패딩과 테두리 포함X<br>
box-sizing:border-box; => 요소의 사이즈에 패팅과 테두리까지 포함<br>   

### 선택자
+ html 요소에 css를 적용시킬 태그를 지칭
+ Universal-html 요소 전체에 적용<br> * 선택자를 사용<br>무분별한 남용은 삼가
<hr>

### CSS Box  (inline,block)
#### inline
+ 한 줄에 표시
+ a,img,span태그가 해당
+ 태그로 감싸진 내용만큼만 영역을 차지
+ width와 height로 요소의 크기를 조절X
+ inline은 좌우 margin,padding만 적용가능
<br>
<hr>

### block
+ 개별 요소마다 줄을 바꿈
+ h1,p,div태그가 해당  
+ width와 height로 요소의 크기를 조절 가능
+ 내용과 별개로 자신의 영역을 가짐
<br>
내용을 삭제하더라도 태그가 남아있으면 영역을 가짐
<br>
<hr>

### block은 가지지만 inline은 가지지 못하는 것
width,height,margin,padding
+ inline은 좌우 margin,padding만 적용 가능
+ inline에 적용된 것처럼 보이는 상하 padding은 레이아웃에 영향을 미치지 못함
<br>
<hr>

### inline-block
+ inline과 block의 특징을 모두 포함
+ 줄을 바꾸지 않음
+ block처럼 width와 height를 가짐
+ 상하 margin,padding이 레이아웃에 유효함
+ display:inline-block
<br>
<hr>

### box
+ 구성: (margin(border(padding(content)padding)border)margin)

### margin
:margin == 테두리로부터 다른 요소들까지의 거리<br>
작성법
+ margin: 20px(상하) (띄어쓰기 1번) 30px(좌우);
+ margin: 상 우 좌 하;(위쪽에서부터 시계방향으로 이동)
<br>
<hr>

### border
:border == 내용을 둘러싼 테두리
<br> 
작성법

+ border: 6px solid blue;(하나의 속성에 두께, 유형, 색상 적용가능)
<hr>

### padding
:padding == 내용으로부터 테두리까지의 거리
<br>
작성법

+ padding: 4px;(상하좌우에 모두 같은 값 적용)
+ padding: 4px 6px 4px 6px;(위쪽부터 시계 방향으로 이동)

<hr>

## Box-Sizing
<br>

### content-box
+ 요소 사이즈에 패딩과 테두리 포함X

~~~
div{
    box-sizing: content-box;
    width: 100px;
    padding: 5px;
}
~~~
##### 이 경우 content의 사이즈는 100, padding값은 5씩 부여됨.
<br>

### border-box
+ 요소 사이즈에 패딩과 테두리까지 포함
~~~
div{
    box-sizing: border-box;
    width: 100px;
    padding: 5px;
}
~~~
##### 이 경우 content값은 90, padding값은 5씩 부여됨

<hr>

## CSS 단위
### px,%,rem/em
<br>

### px
:px == 스크린을 구성하는 작은 점

<br>

### %
:부모 요소를 기준으로 크기를 설정
~~~
div.outer{
    width: 100px;
}
div.inner{
    width: 50%;
}
~~~
##### 위의 경우 inner는 outer의 50%인 50px를 크기로 가진다.
<br>

### em/rem
em:부모 요소의 폰트 크기<br>
rem(root em):루트 요소의 폰트 크기
<br>

### em
~~~
div.outer{
    font-size: 20px;
}
div.inner{
    width: 2em;
    /* 
    부모 요소의 폰트 사이즈가 20px => 20px * 2 = 40px; 
    따라서 width: 40px;과 같은 의미
    */
}
~~~
<br>

### rem
~~~
html{
    font-size: 10px;
}

div.inner{
    width: 5rem;
    /*
    html의 폰트사이즈 == 10px
    10px * 5 = 50px
    width: 50px;
    */
}
~~~

통일된 기준을 잡기 위해서는 rem 단위 사용 권장
<br>

### vw / vh
:각 디바이스별 화면의 너비 / 높이를 기준으로 배율 설정

~~~
div.expand{
    height: 100vh;
}
~~~
<br>
<hr>

## 이미지 다루기
<br>

+ 이미지태그는 inline성격을 가지고 있다.
+ 단독으로 크기를 설정할 수 없다.

~~~
<div class="container">
    <img
        src="이미지 경로"
        alt="대체 문구"
    >
</div>
~~~
##### inline성격 상 꾸며주기 쉽게하기 위해 div태그로 감싸준 상태
<br>

~~~
img{
    max-width: 100%;
}
~~~
##### 위의 설정은 부모 영역에서 벗어나지 않도록 이미지의 너비 상한선을 100%로 설정
~~~
img{
    object-fit: cover;
    object-fit: contain;
    object-fit: fill;
}
~~~

##### cover은 이미지를 부모 요소의 영역의 크기 만큼 확대/축소하여 채움<br>contain은 이미지의 비율을 유지하면서 크기를 변경하여 부모 요소를 채움<br>fill은 이미지의 비율을 유지하지 않고 부모 요소의 크기에 맞게 변경하여 채움

<hr>

## Overflow
+ 브라우저 입장에서 요소가 넘치는 것은 에러가 아님

~~~
html
<div class="overflow">
    CSS<br>IS<br>AWESOME
</div>

css
div.oveflow{
    border: 2px solid black;
    width: 180px;
    font-size: 50px;
    /*'-x'는 x축을 스크롤 할 수 있게 해줌, */
    overflow-x: scroll;
    /* 자동으로 스크롤 생성을 해주는 코드 */
    overflow: auto;
}
~~~
##### 위의 코드의 경우 div태그의 content가 테두리 박스를 넘어 표시가 되는 것을 overflow라는 속성을 이용하여 값을 scroll을 주어 박스를 넘어가지 못하게 하고 오버플로우가 발생해 안보이는 content는 스크롤을 통하여 볼 수 있게 하였다.  
<br>

## font
~~~
<div class="container">
    <p>Hello:)</p>
    <p><a>link:)</a></p>
</div>


html{
    font-size: 10px;
}
p{
    /* 
    Hex color: red,green,blue의 값을 각각 16진수로 나타내어 조합 
    */
    color: #008000;
    /* 10px * 0.5 */
    font-size: 0.5rem;
    font-style: italic;
    /* 글씨 굵기 */
    font-weight: bold;
    /* 밑줄 */
    text-decoration: underline;
}

a{
    /* a태그의 밑줄 제거 */
    text-decoration: none;
}
a.link{
    /* 클릭한 적이 없는 링크 */
    color: black;
}
a.visited{
    /* 방문했던 링크 */
    color: black;
}
~~~
##### link,visited 선택자의 순서가 바뀌지 않게 유의해야함
<hr>

## border 꾸미기
+ border의 테두리는 기본적으로 none 값이 적용됨.
~~~
<div class="container">

</div>

.container{
    border-width: 2px;
    border-style: solid;
    border-color: blue;
    /*
    border: 2px solid blue;
    와 같음.
    */
    /* 모서리를 둥글게 해 주는 속성 */
    border-radius: 20px;
}
~~~
<hr>

## 배경 이미지 설정
<br>

+ ### 배경색
~~~
<div class="container">
    <p>
    안녕하세요:)
    </p>
</div>

.container{
    background-color: yellow;
}

p{
    background-color: skyblue;
}
~~~

+ ### 배경 이미지

~~~
<div class="container">
</div>

.container{
    background-image: url('주소값');
    /* 이미지를 반복하지않고 하나만 채움 */
    background-repeat: no-repeat;
    /* 이미지가 온전히 표시되는 것이 우선으로 채움 */
    background-size: contain;
    /* 요소의 배경을 모두 덮는 것이 우선, 비율은 유지하지만 사진이 짤릴 수 도 있음 */
                   : cover;
    /* 이미지는 기본적으로 요소의 중앙에 있지 않음. */
    background-position: center;
}
~~~

<hr>

## 요소 정렬하기
<br>

### 가운데 정렬
+ margin: 0 auto;
~~~
CSS

body{
        /*(상하) (좌우)*/
    margin: 0 auto;
}
~~~

##### 좌우의 margin을 자동으로 맞춤.<br>부모 block 요소의 width를 기준으로 자동으로 margin 계산
<br>    

+ text-align: center;
    + ##### 부모요소가 block이고 정렬하려는 자식의 요소가 inline일때 사용
~~~
<div class="container">
    <img
        src="이미지 주소"
    >
</div>

.container{
    text-align: center;
    /* 블록 요소 내의 인라인 요소를 가운데 정렬 */
}
~~~
##### 위의 코드의 경우 container클래스인 div태그 안에 있는 img태그가 div태그 안에서 가운데 정렬이 되는 것이다.<br>
<hr>
