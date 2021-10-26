# interactive_web2

콜로소 디자이너를 위한 코딩 : 컬럼레이아웃 페이지 공부

## block 값에는 width 와 height 값이 포함되지 않고 플러 되어 계산 되어 진다 <기본 값 content-box>

즉, width와 height는 300px 과 200px 로 각각 잡아 놓았지만 실제 개발자 도구 화면으로 측정시
<strong>370\*270</strong>으로 나오게 되며, 결국에는 차지하는 영역은 더 커지게 된다. 실제 현장에서는
크기는 염두해 주고 작업을 해야 하는데, 요즘에는 box-sizing: border-box를 사용하면 border와 padding의 크기가 width 와 hight의 안에 포함되게 된다.
<strong>작업 전 미리 잡아두게 되어 전체 사이즈를 맞출 수 있게 한다고 한다.</strong> 넣어주는 곳은 reset css 쪽 에 넣어 준다고 한다.

## width 70%?

100%는 내 부모의 width의 폭이 되는데 내 부모의 크기가 예를 들어 500px 일때 두 색션의 100%는 500px이 되는 것

## section 과 section 사이는 공간이 있는 것으로 판단 한다

그래서 section 70% section 30%를 줄때 안 겹쳐지는 이유가 이거 였고, 이것을 겹치게 만드려면 section과 seciton 사이의 공간을 지워 주면 된다. 지우는 방법은, </seciton> <section> ➡️ </section><section>
라고 하지만 코드 보기에는 너무 안 좋게 보이므로 다른 방법이 있다고 한다.

<strong>진짜 없애는 방법! </strong> 부모 요소에 font-size를 0으로 놓고 자식 요소에 font-size를 다시 부여 !
그리고 안 맞는 것을 맞추기 위한 <strong>vertical-align ="top"</strong>으로 맞춰 준다.

display=inline-block 을 이용한 이중 컬럼 만들기 끝

## float를 이용한 컬럼 만들기! <보통 많이 사용한다>

image에 float left 속성을 주게 되면 이미지 오른쪽 기준으로 글짜 들이 모이게 된다.

section 전체 속성에 float left를 주게 되면 footer 까지 float 영향을 받게 된다

그럴때 해결법은 ❗️<strong>footer에 clear:both, clear:left 를 주게 되면 해결된다.</strong>

부모 요소에 float를 줄시 자식 요소들은 float되게 되므로 top에 떠있게 된다.

-남는 부분은 부모 요소 끝 부분에 div를 주어 clear 를 주면 된다는데 무슨 말인지 모르겠다 ...

컨텐츠 색션에 가상요소를 주어 굳이 태를 사용하지 않더라도 사용 하다고 한다.

## position ?

positon : absolute를 주게 되면 절대 위치가 되게 된다.

앱솔루트를 주게 되면 띄어 지게 되서 공간을 차지 안하게 되고 A 위치로 가게 된다.

기본적인 static 보다 위로 올라가게 된다.

b에 position을 주게 되면 b가 올라가게 되는데
그 이유는 나중에 써준 코드가 읽어지게 되서 그렇다.

다른 것을 올리고 싶으면? z-index를 써주면 된다.

### relative

속성 값에 relative나 absolute를 주게 되면 원래 static 이였던 포지션으로 부터 이동하게 된다.

부모 값을 relative를 주면 자식 요소들은 부모를 따라 그 위치를 잡게 되어 있다.

굉장히 유용한 기능 이다.

## position absolute와 fixed는 width 값을 따로 줘야 한다.

### sticky?

이미지를 넣었을때 내가 지정한 position에 다다르기 전까지 계속 떠있는 것 같은 효과를 줄수 있다.

사용 용도 : 광고 배너 등
