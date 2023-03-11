# kokoa-clone

- HTML/CSS
<details>
<summary>⬇️ Nomad Coders Kokoa clone Lecture Note</summary>
<div markdown="1">


# 1. Intro

- **HTML** : 기본 뼈대(이게 title, link 라는 것들이야~)
- **CSS** : 근육(얘는 초록색이야~)
- **JS** : 뇌

로 비유할 수 있다.

# 2. HTML

- 파일명/폴더명은 항상 전부 소문자로.(에러 남)
- "여기부터 여기까지가 뭐뭐야~"의 역할을 HTML이 해주는데, 이때 "여기"에 해당하는 게 태그!
- tag 중에서 **a** 는 anchor(닻)을 의미한다. 쉽게 생각하면라고 생각할 수 있다.
    
    link
    
    - (다른 웹사이트로 가는 것)
    - 얘는 정보가 더 필요한데 link 태그는 **href(Http reference)**가 필요하다. 어디로 가는지.
    - **target**이라는 attribute(기본값은 _self)도 있다(뒤로 가기 했을 때 어디로 가는지). 이외에도 엄청 많은 attribute들이 있음
- img 는 self-closing tag
    - src는 img에서만 쓰인다
        - 폴더 내에 파일이 있으면 그냥 파일명.확장자 하면 되고
        - 폴더 밖에 파일이 있으면 경로/파일명.확장자 로 작성해준다.
- HTML 파일이라면 전부 <!DOCTYPE html>로 시작해야 한다!
    - 브라우저에게 이건 텍스트가 아니라 html 파일이라고 알려준다.
- HTML 파일 구조⬇️

```
<!DOCTYPE HTML>
<html>
		<head>
		</head>
	<body>
		<h1>
		</h1>
		<a href="~~" target="~~">
		<img src="~~"/>
	</body>
</html>

```

- **head** : 페이지에 관한 설정해주는 곳
    - 예: title
    - head 태그에 있는 애들은 **invisible**하다
- **meta** : 부가적인 정보. content, name으로 이루어짐. self closing tag.
    - **charset**은 브라우저에게 text를 어떻게 그려달라고 할지를 말하기 때문에 중요하다.(한글, 특수문자 깨지지 않게 해줌.)
        - charset=”utf-8”
- **lang** : 검색 엔진들한테 우리 사이트의 사용 언어를 알려주는 유용한 역할을 함.
- **description** : 검색엔진이 검색할 때 찾는 태그
- 태그를 전부 외우는 건 불가능하므로 html/css 관련 **검색**을 해준다.
    - 이때 mdn 키워드를 활용하면 로 안내해준다.
        
        “Mozilla developer Network”
        
    - w3 schools 말고 mdn 사이트 쓸 것!(이유?)
- **enabled** 는 true와 비슷하다
- **label** : form에 question 추가 가능, 박스 체크 클릭하는 것도 가능
    - **input과 함께 사용**되어야 작동함(label for~, input id ~)
- **id** :
    
    element 당 하나의 id만 가질 수 있으며 고유하다
    
    - css가 가능한 이유가 html에 id가 있기 때문
- **div** : division. 박스로 생각하면 편하다. 박스에 태그들을 넣어주면 기본적으로 box들은 양옆에 서로 붙어 있을 수 없다.(기능은 있지만 아무 값도 없다고 이해할 수 있다)
- **span** : 짧은 텍스트를 위한 태그
- **tag**에는 의미가 없는 애들도 있다~(**non-semantic tags**)
- **semantic tags**
    - **header** : head와 다르다. div 대체 가능. 이름만 봐도 웹사이트의 header구나 알 수 있음. 같은 기능이지만 의미 짐작이 가능하다. 검색엔진도 이해 가능.
    - 다른 semantic tags 예시: main, footer(꼬릿말),aside, …
- **--------------------------------------------------------**
- **Visual Studio Code 팁**
- 같은 단어를 동시에 바꿔주고 싶을 때 → 선택하고 **cmd+d**
- 동시에 여러 군데 글씨 입력하고 싶을 때는 **alt**
- **--------------------------------------------------------**

# **3. CSS**

- **HTML과 같이 두는 경우** : 하고 스타일 태그 안에 css 코드 짜주는 것.
    
    <head>에 <style> 사용
    
- **분리해서 두는 경우** :  만들고 html 파일에 **<head> 안에 <style>에 <link href = “css파일명” rel = “stylesheet”/>**라고 하기
    
    css 파일 따로
    
    - 분리하는게 더 다양한 html 파일에 적용 가능
- 중괄호 Curley braces
- CSS 포맷 : **Selector{Properties}**, **세미콜론**으로 속성 마무리 해준다.
    - What is Selector? => It is a pattern of elements and other terms that tell the browser which HTML elements should be selected to have the CSS property values inside the rule applied to them
- property 이름에는 띄어쓰기 X
- CSS는 **Cascading**(위에서 아래로 내려오는)이기 때문에 이에 따라 마지막으로 명령한 것을 따른다.
    - 즉, 코드 순서에 영향을 받는다.
- **block vs inline**(옆에 누가 못 온다 vs 올 수 있다)
    - inline : 아주 작은 글, 링크, 그림 등등
    - block : 대부분의 block. header도 마찬가지.
    - block이 아닌 것 span. a. image 등등
- block을 inline으로 바꾸기 또는 반대 : **display 속성**
    - inline-block : block으로 인식해서 높이, 너비 가질 수 있고 margin 가질 수 있고 다른 요소도 가질 수 있음 ⇒ 문제가 많음(default로 주어진 공간, 정해져있는 형식 등 문제가 많다), 반응형 디자인(responsive vdesign) 미지원..
    - **대신 flexbox!**
- **inline은 너비와 높이가 없다!**
    - 따라서 상하 **margin 가질 수 없다.**
    - padding은 다 가능
- block 특성
    - margin, padding, border ok
- **margin** : box의 경계 바깥에 있는 공간
    - margin: (vertical) (horizontal);(상하 좌우)
    - margin: (top) (right) (bottom) (left); (시계방향)
    - collapsing margins : 경계가 같은 요소들의 margin은 같게 취급(vertical로만 적용되는 현상)
- **padding**: 경계 안쪽에 있는 공간
- 특정 id 가리키는 방법 : **#id{}**
- **border** : inline, block 모두에 적용된다
- {} : 전체에 적용
- class : **.클래스명**
- **flexbox** : 2차원(2d) 레이아웃에서 작동 잘함
    - 3가지 규칙
        - 자식 엘레먼트에 아무것도 적지 말기,
            
            부모 엘리먼트에만 말한다
            
        - **주축 수평, 교차축은 수직**
    - **display: flex**
        - **justify-content** 등 사용 가능()
            
            주축에 적용
            
        - **align-items** (에 적용, 기본적으로는 수직)
            
            교차축
            
        - **wrapping** : 창을 줄이면 붙는 걸 말하는 듯? 이게 기본값인데 flex-wrap속성으로 조정 가능하다
- **vh** : viewport height(screen height, 비율)
- 수직, 수평 적용을 바꾸고 싶을 땐 **flex-direction**을 수정하면 된다
    - **default : row(수평)**
        - column으로 바꾸면 주축이 수직으로 바뀐다.
- **position** : 위치 조정할 때
    - **position: fixed;** : 스크롤 해도 위치 계속 고정
    - top, bottom, left, .. 등 아무거나 수정하면 다른 애들이랑
        
        다른 레이어에 위치하게 됨
        
    - **position:static;** : 레이아웃이 박스 처음 위치하는 곳에 두는 걸 의미
        - **relative** : 조금씩 옮기고 싶을 때, 이거 설정하면 top bottom left right 가 unlock된다(요소가 처음 위치한 곳 기준으로 수정하는 것)
        - **absolute** : 가장 가까운 relative 부모 기준으로 이동시켜줌
- **pseudo selector** : 세부적으로 element 선택해줄 때 사용
    - **:** 써주고 그 뒤에 옵션 선택
    - 이게 id나 class 만드는 것보다 훨씬 좋은 방법! (html 안 건드리고 css에서만 작업함)
    - **first-child, nth-child(), even/odd**
    - 2n, 2n+1, 3n+1, 4n+1, …(몇 개마다 하고 싶은지 기준)
- **combinators** : **>**(바로 밑 자식), **+**(형제)
    - The final selectors we will look at are called combinators, because they  in a way that gives them a useful relationship to each other and the location of content in the document. (ref : mbn web docs)
        
        **combine other selectors**
        
    - 부모 자식 {} ⇒ 부모 안에 있는 자식을 찾아서 설정함
    - ~ : 형제와 형제 관계인데 바로 뒤에 올 필요 없음
    - ~= sth : sth을 포함하고 있다
- **states**
    - active : 클릭한 상태
    - hover over: 마우스 커서가 대상 위에 있을 때
    - focus: 키보드로 선택되었을 때
    - visited : 링크에만 적용됨. 방문했던 링크.
- **::placeholder** : placeholder 스타일링 가능하게 해줌
- **rgba** : a는 투명도!
- chrome extension - color picker 추천
- **:root** : **document의 뿌리**가 되는 것. 컬러 지정해서 저장하고 싶으면 —main color를 여기에 저장
- 이후 **var로 불러와서** 쓰면 된다!O.O

⇒ **custom property / variables**

- Custom properties(sometimes referred to asCSS variables or cascading variables) are set using and are accessed
    
    entities defined by CSS authors that **contain specific values to be reused** throughout a document.
    
    custom property notation (e.g.,
    
    - -main-color: black;
    
    )
   
    

- - - 변수명(dash 2개에 변수 이름!)

# **4. Advanced CSS**

- JS 말고 CSS에서도 효과를 줄 수 있다
- **Transitions**
    - state에 따라 바뀌는 property를 갖고 있으면 사용되는 것.
    - 다른 상태로의 변화를 애니메이션으로 만드는 것
    - transition은 state가 없는 곳에 작성해줘야(원래 element 있는 곳에)
    - 변화시킬 거면 대상이 state 관련된 곳과 기본 상태에 대한 곳 모두에 있어야 한다.
    - [matthewlein.com](http://matthewlein.com/) 추천(transition 차이 잘 보여줌)
    - ease-in-out : 처음에 느리게 시작, 가속, 느려짐
- **Transform**
    - **border-radius**: 50%;는 원이 된다~
    - **rotateY(~deg)** : 3D처럼 Y축을 중심으로 돌아간다
        - (90도면 아예 일자라 안 보임)
    - **translateX(-10)** : 왼쪽으로 10만큼 이동
- transition, transform 함께 쓸 수 있다~
- transform mdn 검색해서 사용해볼 것
- **animations**
    - **@keyframes 애니메이션이름 { }**
    - 1~100까지 을 가질 수 있다. 아니면 from -to
        
        여러 개의 스텝
        
    - CSS animations 검색해서 찾아보면 다양한 예시들이 더 있다.
    - opacity : 투명도
- **Media query**
    - CSS만 사용해서 **스크린 사이즈**를 알 수 있는 방법
    - 스크린 사이즈에 맞게 변경 가능
    - **@media screen and ( ) { }** 요런 식으로 해줘야 함
    - **and**로 연결
    - **@media print**

==============================================

💡 **element 선택 방법 정리**

- 태그 이름만 쓰기
- 점 쓰고 클래스 이름 쓰기
- id 쓸 때처럼  쓰기
    
    #에 id 이름
==============================================
</div>
</details>
