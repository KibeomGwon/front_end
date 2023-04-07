# CSS NEXT LEVEL

## Float
: 떠오르다.<br>자식이 부모로부터.<br>=> margin을 없애버리다.

각 블록들은 부모의 width만큼 margin값을 가짐.<br>
float는 부모로부터 독립적으로 만들어서 그 margin값을 없애버리는 것

~~~
div{
  /* 왼쪽으로 float정렬을 하게 함 */
    float: left;
}
~~~

<br>

## Clear
: float로 없어진 margin영역을 무시하지 올라가지 않도록 처리

~~~
.div1{
    float: left;
}
.div2{
    /* div2의 margin은 사라지지 않음 */
    clear: left;
}
~~~

##### 위의 코드는 div1의 없어진 margin영역을 div2가 채우지 않게하는 코드
<br>

+ clearfix
: clear라는 속성으로 Layout을 바로잡는 기법<br>

~~~
(범람을 막고 싶은 요소 == float로 margin이 없어짐)::after {
    content: " ";
    display: block;
    clear: both;
}
~~~
##### 위의 코드 그대로 작성해야 함.
<br>

## Flex
: 가로 배치
+ Flexbox   
    + flex container: {display:flex;}를 선언한 부모 요소.
    + flex item: flex container의 자식 요소.(배치를 원하는 요소)
    + main axis: 가로 배치의 주축; 세로의 보조축
    + cross axis: 세로 배치의 주축; 가로 배치의 보조축

~~~
<div class="container">
    <div></div>
    <div></div>
    <div></div>                         
</div>

.container{
    display: flex;
}
~~~

##### 위의 코드를 화면으로 나타내면 .container의 자식요소인 모든 div가 float 상태가 되면서 왼쪽으로 정렬이 된다.

<br>

~~~
.container{
    display: flex;
    justify-content: space-between;
}
~~~
##### 위의 코드는 정렬 상태를 맨 첫번째 div는 맨 왼쪽, 끝 div는 화면 맨 오른쪽, 2번쨰 div는 정 중앙에 오게 배치를 한 것이다.
<br>

## Position

+ static
+ relative
+ absolute
+ fixed
+ sticky

### relative
:원래 위치를 기준으로 요소를 움직일 때 사용
~~~
div{
    position: relative;
    left: 50px;
}
~~~
##### 원래 위치에서 50px 떨어진 곳에 위치시킴
<br>

### absolute
:다른 요소 ex) margin 등에 구애 받지않고 자유롭게 움직임
<br>부모를 기준으로 위치만 변경 
<br>

### fixed
:브라우저 창을 기준으로 고정된 위치<br>
ex) 웹 페이지 상단의 고정된 메뉴 바
~~~
div{
    position: fixed;
    bottom: 0;
    right: 0;
}
~~~
<br>

### sticky
:스크롤로 특정 위치에 도달하면 고정

~~~
div{
    position: sticky;
    top: 0;
}
~~~
##### 위의 코드는 div가 상단에 0에 위치해 있을때 스크롤로 인해 내용이 사라지지 않고 그대로 화면 top: 0 에 고정이 된다.
<br>

## Grid
:페이지의 가이드 라인
+ container: Grid system이 적용될 영역
+ row: 행,가로,부분, float된 column.<br>
요소가 흘러 넘치지 않게 하는 역할
+ column: 열.세로 부분.요소의 위치 결정에서 실질적인 역할 수행
+ gutter: row와 column사이의 간격