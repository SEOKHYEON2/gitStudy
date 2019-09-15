a(anchor)
~~~
태그 생략 : 불가능

DOM interface : HTMLAnchorElement

속성

download : 이 속성이 존재할 경우 작성자가 리소스를 다운로드하는 데에 하이퍼 링크를 나타낸다
           만약 이 속성이 값을 가질 경우 유저가 링크를 클릭하고 나오는 저장창에 미리 채워진 파일 이름의 값으로 사용된다.

href : URL이나 'URL 조각' 연결할 대상을 가리킨다.
       'URL 조각'은 #가 달린 이름이며 현재 문서에 있는 내부의 목표 지점(ID속성을 가진)을 의미한다.
       ex)<a href="#top">Return to top</a>

hreflang : 이 속성은 링크된 리소스가 어떤 언어로 작성되었는지 명시한다.

rel : 대상 개체와 링크 개체의 관계를 지정한다. 값은 공백으로 구분된 링크 유형 목록입니다.

target : 링크한 URL을 어디에 표시할건지 지정한다. 가능한 값은 브라우징 문맥(탭,창)
         <iframe>의 이름 또는 키워드이다.
         _self : URL을 현재 브라우징 문맥에 표시한다. Default
         _blank : URL을 새로운 브라우징 문맥에 표시한다. 보통 새 탭이지만 사용자 설정으로 새 창으로 바꿀 수 있다.
         _parent : URL을 현재 브라우징 문맥의 부모에 표시한다. 부모가 존재하지 않으면 _self와 동일하게 행동한다.
         _top : URL을 최상단 브라우징 문맥(현재 문맥의 부모면서 자신의 부모가 존재하지 않는, 제일 높은 문맥)에 표시한다. 부모가 존재하지 않으면 _self와 동일하게 행동함.

응용으로 a의 내용 (contents)로 이미지를 넣을 수 도 있다.

mailto 링크를 사용해서 사용자의 이메일 프로그램에서 열리는 버튼이나 링크를 만들어 새 메시지를 보낼 수 있도록 한다.
~~~
abbr
~~~
속성 

title : 이 친구로 약어의 풀네임을 설명한다. 혹은 반대로 약어를 명시해주기도 한다.

응용
dfn과 같이 쓸 수 있다.
ex) <dfn id="spec">Specification</dfn>(<abbr title="Specification">spec</abbr>)


약어를 나타낼 때 사용한다 사용법은

<abbr title="Hyper Text MarkUp Language">HTML</abbr>
<abbr title="HTML">Hyper Text MarkUp Language</abbr>
~~~
address
~~~
address 태그 내부의 HTML 요소들은 사람이나 사람 또는 조직에 대한 연락처 정보를 제공하는 것으로 나타낸다.
일반적으로 <footer>의 요소 안에 있을 수 있다.

ex)
<address>
    <a href="mailto:jim@rock.com">jim@rock.com</a><br>
    <a href="tel:+13115552368">(311) 555-2368</a>
</address>
안의 친구들은 

시작,종료 태그는 필수다.

DOM 인터페이스 : HTMLElement Gecko 2.0

속성

전역 속성(Global Attribute)

즉 이 태그 안에 감싸줌으로써 연락처 정보를 구분하기가 쉽다.
~~~
area
~~~
이 요소의 속성엔 전역 속성이 포함된다.

속성

alt : 이미지가 안뜰 때 대체되는 텍스트. href 속성을 쓸 때만 쓰자.

coords : 핫스팟 영역의 좌표를 지정하는 값 집합이다. 값의 수와 의미는 shape속성에 지정 값마다 다르다.
    rect 또는 square : 좌표 값은 왼쪽, 위, 오른쪽, 아래쪽의 두 x,y쌍이다.
    circle : 값은 x,y,r이다. x,y은 원의 중심을 지정하는 쌍이며 r은 반지름의 값이다.
    poly 또는 polygon : 값은 다각형의 각 점에 대한 x,y 세트다. x1,y1,x2,y2,x3,y3
단위는 px(픽셀)다.

download : 이 속성이 존재할 경우 작성자가 리소스를 다운로드하는 데에 하이퍼 링크를 나타낸다
           만약 이 속성이 값을 가질 경우 유저가 링크를 클릭하고 나오는 저장창에 미리 채워진 파일 이름의 값으로 사용된다. 

href : URL이나 'URL 조각' 연결할 대상을 가리킨다.
       'URL 조각'은 #가 달린 이름이며 현재 문서에 있는 내부의 목표 지점(ID속성을 가진)을 의미한다.
       ex)<a href="#top">Return to top</a>

hreflang : 이 속성은 링크된 리소스가 어떤 언어로 작성되었는지 명시한다.

referrerpolicy : 리소스를 가져올 때 사용할 참조자를 나타내는 문자열이다.

rel : 대상 개체와 링크 개체의 관계를 지정한다. 값은 공백으로 구분된 링크 유형 목록입니다.

shape : 관련 핫스팟의 모양이다. 위의 coords와 관련이 있다.
        rect, square, circle, poly, polygon

target : 링크한 URL을 어디에 표시할건지 지정한다. 가능한 값은 브라우징 문맥(탭,창)
         <iframe>의 이름 또는 키워드이다.
         _self : URL을 현재 브라우징 문맥에 표시한다. Default
         _blank : URL을 새로운 브라우징 문맥에 표시한다. 보통 새 탭이지만 사용자 설정으로 새 창으로 바꿀 수 있다.
         _parent : URL을 현재 브라우징 문맥의 부모에 표시한다. 부모가 존재하지 않으면 _self와 동일하게 행동한다.
         _top : URL을 최상단 브라우징 문맥(현재 문맥의 부모면서 자신의 부모가 존재하지 않는, 제일 높은 문맥)에 표시한다. 부모가 존재하지 않으면 _self와 동일하게 행동함.


시작 태그가 있어야하고 종료 태그가 없어야한다.

ex) <area shape="circle" coords="75,75,75" href="left.html" alt="Click to go Left">

걍 a태그의 도형화라고 생각하면 될듯
~~~
article
~~~

속성

전역 속성(Global Attribute)

시작 태그와 종료 태그는 필수고 각 게시물은 <article>요소에 포함될 수 있다.
하나 이상의 <section>가 포함된다.

DOM 인터페이스 : HTMLElement

사용법 메모
1. 각 요소 <article>은 일반적으로 (<h1>-<h6> 요소)를 <article> 요소의 자식으로 포함해 식별한다. 
2. 중첩이 된다
3. article의 작성자 정보는 address 요소로 제공할 수 있지만 중첩 article요소에는 적용 X

즉 말그대로 기사관련 내용을 감싸줄 때 사용하나봐
~~~

aside
~~~


속성

전역 속성(Global Attribute)

시작 태그와 종료 태그는 필수다.


ex) <aside>
    <p>The Rough-skinned Newt defends itself with a deadly nenu</p>
    </aside>
   
사용법 메모
1. 이러한 종류의 텍스트는 주요 흐름의 일부로 간주되므로 요소를 사용해 괄호로 묶은 텍스트에 <aside>태그를 지정하지 마십쇼.

단락을 꾸미고 싶을 때 사용한다거나..

ex) <article>
        <p>
            The Disney movie <cite> The Little Mermaid </cite> was
            first released to theatres in 1989.
        </p>
        <aside>
            <p>
                The movie earned $87 million during its initial release.
            </p>
        </aside>
        <p>
            More info about the movie...
        </p>
    </article>
~~~    


audio
~~~

문서의 사운드 내용을 포함하는데 사용한다.

ex)
<audio
    controls
    src="/media/examples/t-rex-roar.mp3">
        your browser does not support the
        <code> audio </code> element.
</audio>

속성

autoplay : boolean 타입이다. 지정된 경우 전체 오디오 파일의 다운로드가 완료될 때까지
           기다리지 않고 가능한 빨리 오디오가 자동으로 재생을 시작한다.

controls : 이 속성이 있으면 브라우저는 사용자가 볼륨, 탐색 및 재생 일시 정지 / 재개를
           포함하여 오디오 재생을 제어할 수 있는 컨트롤을 제공한다.

duration : 오디오의 지속 시간 (총 길이)를 초단위로 나타내는 배정 밀도 부정 소수점이다.
           요소에 매체가 없거나 매체가 유효하지 않으면 리턴 값은 NaN이다.
           끝이 없을땐 +Infinity

loop : boolean 타입이다. 지정된 경우 오디오 플레이어는 오디오 끝에 도달하면 시작 부분으로 자동 검색한다.

muted : boolean 타입이다. 오디오가 처음에 침묵되는지 여부를 나타내는 부울 속성이다. 기본 값은 false다.

src : 포함할 오디오의 URL이다. HTTP Access Control이 적용된다.
      <source>대신 오디오 블록내의 요소를 사용해 포함할 오디오를 지정할 수 있다.

preload : 힌트를 브라우저에게 제공한다.
        none : 오디오를 미리 로드하지 말아야함을 의미한다.
        metadata : 오디오 메타 데이터만 가져오는 것
        auto : 사용자가 사용하지 않아도 전체 오디오 팔일을 다운로드할 수 있다.

JS의 HTMLMediaElement API와 함께 사용해 기능을 연결한다.

~~~
b
~~~

요약의 키워드, 리뷰의 제품 이름 또는 굵은 글씨체(특별히 안중요한)를 포함하는 다른 텍스트 범위와 같은 경우에 사용하자..

속성

전역 속성(Global Attribute)


시작 태그와 종료 태그 모두 필수다

~~~
base
~~~
문서에 포함된 모든 상대 URL에 사용하는 기본 URL을 지정한다.
문서에는 하나의 <base>요소만 있을 수 있다.



속성

href 위에서 배웠잖아~

target 위에 꺼랑 공통


시작 태그만 있어야 한다.


ex) 
<base href="http://www.example.com/"> 지정을 해주면
<a href="a">Anker</a>
Anker를 누르면 http://www.example.com/a로 자동으로 간다.

ex)<base href="http://www.example.com/" target="_blank">로 해주면
새탭이 뜨면서~ 저 url이 매핑이 되는것이지..
~~~



bdi 
~~~
1. 웹에서 텍스트를 동적으로 삽입하고 삽입되는 텍스트의 방향을 모르는 경우 유용하다.
2. 브라우저의 양방향 알고리즘에 포함된 텍스트를 주변 테그슽와 분리하여 처리한다.

LTR, RTL 친구들을 쉽게 처리할 수 있겠지

속성

전역 속성

시작 태그와 종료 태그 필수다..

ex)
<ul>
    <li><bdi class="name">RTL텍스트</bdi> - 1st place </li>
    <li><bdi class="name">LTR텍스트</bdi> - 2nd place </li>
</ul>
~~~

bdo
~~~
1. 텍스트의 현재 방향성을 재정의한다.


속성

dir
    ltr : 텍스트가 왼쪽에서 오른쪽으로 이동해야 함을 나타낸다.
    rtl : 텍스트가 오른쪽에서 왼쪽으로 이동해야 함을 나타낸다

ex) 
<p>This text will go left to right.</p>
<p><bdo dir="rtl">This text will go right to left. </bdo></p>
~~~

blockquote
~~~
1. 텍스트가 확장 인용되고 있음을 나타낸다. 일반적으로 들여 쓰기로 시각적으로 렌더링된다.
2. cite 속성을 사용해 인용 소스에 대한 URL을 제공할 수 있다.

속성

인용된 "정보"에 대한 소스 문서 또는 메시지를 지정하는 URL이다.



시작 태그와 종료 태그는 모두 필수다.

DOM 인터페이스 : HTMLQuoteElement

<blockquote cite="https://www.huxley.net/bnw/four.html">
    <p>Words can be like X-rays, if you use them properly-they'll</p>
    <footer>-Aldous Huxley, <cite>Brave New World</cite></footer>
</blockquote>
~~~

body
~~~
HTML 문서의 내용을 나타낸다.. 하나의 문서에 하나의 body만 있을 수 있다.

DOM 인터페이스 : HTMLBodyElement
                document.body를 통해 요소에 엑세스할 수 있다.


속성

onafterprint : 사용자가 문서를 인쇄한 후 호출하는 기능

onbeforeprint : 사용자가 문서 인쇄를 요청할 때 호출하는 기능

onbeforeunload : 문서가 언로드 될 때 호출하는 기능

onblur : 문서가 포커스를 잃을 때 호출하는 기능

onerror : 문서를 제대로 넣지 못하면 호출하는 기능

onfocus : 문서가 포커스를 받을 때 호출하는 기능

onhashchange : 문서의 현재 주소의 조각 식별자 부분(해시('#')문자로 시작)이 변경된 경우 호출하는 기능

onlanguagechange : 선호하는 언어가 변경되었을 때 호출하는 기능

onload : 문서 로딩이 완료되었을 때 호출하는 기능

onmessage : 문서가 메시지를 받았을 때 호출하는 기능

onoffline : 네트워크 통신이 실패했을 때 호출하는 기능

ononline : 네트워크 통신이 복구되었을 때 호출하는 기능

onpopstate : 사용자가 세션 히스토리를 탐색했을 때 호출하는 기능

onredo : 사용자가 실행 취소 트랜잭션 내역에서 앞으로 이동할 때 호출하는 기능

onresize : 문서 크기를 조정할 때 호출하는 기능

onstorage : 저장 영역이 변경되었을 때 호출하는 기능

onundo : 사용자가 실행 취소 트랜잭션 내역에서 뒤로 이동했을 때 호출하는 기능

onunload : 문서가 사라질 때 호출하는 기능

ex)
<html>
    <head>
        <title>DD</title>
    </head>
    <body>
        <p>sisi</p>
    </body>
</html>


~~~

br
~~~

텍스트에서 줄 바꿈 해줌

잘 안씀 ㅇㅇ;;

DOM 인터페이스 : HTMLBRElement
~~~
button
~~~
버튼 만들어줌


속성

autofocus : boolean 속성 페이지가 로드될 때 버튼에 입력 포커스가 있어야 함을 지정한다.
            문서에서 하나의 요소만이 이 속성을 가질 수 있다.

disabled : boolean 속성 사용자가 버튼과 상호 작용하지 못하게한다. 

form : 이 속성은 값이 존재해야하는데 만약 값이 존재하지 않다면 <button> 요소의 상위 <form>
       요소와 연관된다.(있다면 말이지..)
       이 속성을 사용하면 <button> 요소의 <form>하위 <form>요소가 아니라 문서의 어느 위치에서나 요소와 요소를 연결할 수 있다.


formaction : 버튼이 제출한 정보를 처리하는 URL이다. 
             지정된 경우 버튼 양식 소유자의 action 속성보다 우선시 한다.

formenctype : submit 버튼인 경우 서버에 양식을 제출하는 데 사용되는 양식 데이터 인코딩을 지정한다.

formmethod : submit 버튼인 경우 브라우저가 양식을 제출하는 데 쓰는 HTTP 메서드를 지정한다.

formnovalidate : boolean 속성 submit 버튼인 경우 양식을 제출할 때 유효성을 검증하지 않도록 지정한다.

formtarget : submit 버튼인 경우 속성은 작성자가 정의한 이름이거나 양식을 제출해 응답을 표시 할
             위치를 나타내는 표준화 된 밑줄이 붙은 키워드다.

name : value 버튼의 이름으로 양식 데이터의 일부로써 버튼과 쌍으로 제출된다.

type : 버튼의 기본 동작이다.
        submit : 양식 데이터를 서버에 제출한다.
        reset : 모든 컨트롤을 초기 값으로 재설정한다.
        button : 기본 동작이 없으며 아무 작업도 수행하지 않음

value : 버튼의 초기 값이다. name 양식 데이터와 함께 제출될 때 버튼과 연관된 값을 정의한다.
        이 값은 양식이 제출될 때 매개 변수로 서버에 전달된다.

Tip : 버튼이 제출용이 아닌이상 button type으로 설정해라.. 안그러면 양식 데이터 제출하고
      양식 데이터를 제출하고 존재하지 않는 응답을 로드해 문서의 현재 상태를 손상시킬 수 있다.

ex) <button name="button">Click me</button>
~~~

canvas
~~~
캔버스 스크립팅 API 또는 WebGL API와 함께 사용해서 그래픽 및 애니메이션을 그린다.

속성

height : CSS 픽셀의 좌표 공간 높이다. default 150px

moz-opaque : 반투명도가 중요한지의 여부를 캔버스에 알린다.

width : CSS 픽셀의 좌표 공간 너비다. default 300px

ex)
<canvas id="canvas" width="300" height="300"> DDDD</canvas>

긍게 결국 API를 같이 써서 그림판같은거 만들 때 쓰는 그거네
~~~
caption
~~~
1. 테이블의 캡션(또는 제목)을 지정하고, 사용된 경우다. 
2. 항상 첫번째 자식은 <table>이다..

ex) <table>
        <caption>EEE</caption>
        <tr>
            <th>LL</th>
            <th>EE</th>
        </tr>
        <tr>
            <td>user1</td>
            <td>usr2</td>
        </tr>
        <tr>
            <td>ueee</td>
            <td>33333</td>
        </tr>
    </table>

테이블 바로 윗칸에 EEE 글씨가 있는거지.
tr은 테이블의 행을 뜻한다.
th는 테이블의 테이블의 head즉 제목이되는 셀이다.
td는 셀이다. 


시작 태그와 종료 태그는 필수다.
~~~
cite
~~~
인용한 것에 대한 정보를 알려줄 때 사용된다

ex) <cite>Nineteen Eighty-Four</cite> 이런식
인용될 수 있는 작품들은 엄청 많다
ex)책, 조각품, 웹 페이지, 연구 논문, 그림 ,블로그 게시물, 수필, 시, 오페라, 트위터 등등
~~~

code
~~~
텍스트가 컴퓨터 코드의 짧은 단편임을 나타내기 위해 의도된 방식으로 스타일의 내용을 표시한다.

ex) <code> push() </code> 
ex) <code> selectAll() </code>

DOM 인터페이스 : HTMLSpanElement

속성

전역 속성(Global Attributes)
~~~
col
~~~
테이블 내의 열을 정의하고, 모든 공통 셀에 공통적 의미를 정의하기 위해 사용된다.
일반적으로 <colgroup>요소 안에서 자주 쓴다.

column말하는거임 ㅇㅇ;;

ex)
<colgroup> 
    <col>
    <col span="2" class="batman">
    <col span="2" class="flash">

속성

사실상 span만 씀 연속되는 열의 수를 지정
~~~
colgroup
~~~
테이블 내 컬럼의 그룹을 정의한다
~~~

data
~~~
1. 내용이 시간 또는 날짜와 관련된 경우 <time>요소를 사용해야한다
2. 주어진 내용을 연결한다.

ex)
<ul>
    <li><data value="398">Mini Kec</data></li>
    <li><data value="399">Mini Mango</data></li>
    <li><data value="400">Mini Banana</data></li>
</ul>

이러면 제품 Mini Kec의 번호는 398로 매칭되고 나머지 친구들도 각각 399, 400으로 매칭된다.
~~~

datalist
~~~
<datalist>는 <option>소자의 그룹이라고 생각할 수 있을 듯
<option> 기타 제어에 사용할 수 있는 값을 나타내는 소자이다.

ex)
<datalist id="ice-cream">
    <option value="Chocolate">
    <option value="mint">
    <option value="mango">
    <option value="gull">
    <option value="gul">
</datalist>
~~~
dd
~~~
선행 (<dd>)친구가 용어에 대한 설명,정의,또는 값을 뜻한다 (<dt>)용어를 뜻하고  (<dl>)친구가 list를 뜻한다

ex)

<dl>
    <dt>Beast of Bodmin</dt>
    <dd>A large feline </dd>
    
    <dt>Mro</dt>
    <dd>A sea serpent.</dd> 
</dl>

속성

nowrap

이 속성의 값이 yes로 설정되면 테스트가 줄 바꿈되지 않는다. default = no임..
~~~

del
~~~
문서에서 삭제된 텍스트의 범위를 나타낸다.

ex) <del>nothing</del>
~~~
ins
~~~
del 요소의 반대 의미로 추가된 텍스트의 범위를 나타낸다.

ex) <ins>no code</ins>

~~~
dl
~~~
이 요소의 일반적인 용도는 용어집을 구현하거나 메타 데이터(키-값 쌍의 목록)를 표시한다
이 요소안에 dd,dt가 들어있음 ㅇㅇ;;
~~~
dt
~~~
설명이나 정의 목록을 사용한다.
~~~
em
~~~
스트레스 강조의 용도로 사용한다. 사용하면 내용(content)가 기울임 꼴이 된다.

<i>와의 차이점은 용도의 차이가 있다. 효과는 똑같지만.
<em> : 내용의 스트레스 강조
<i> : 외국어, 가상의 인물 사고와 같은 일반적인 산문에서 시작된 텍스트를 나타낸다.
~~~
fieldset
~~~
label 뿐만 아니라 여러 그룹을 컨트롤한다.

ex)
<fieldset>
    <legend> Choose one </legend>
       
    <input type="radio" id="kraken" name="monster">
    <label for="kraken">KRAKEN</label>

    <input type="radio" id="kraken" name="monster">
    <label for="kraken">KRAKEN</label>

    <input type="radio" id="kraken" name="monster">
    <label for="kraken">KRAKEN</label>
</fieldset>

속성

disabled : boolean 속성 
           안의 내용을 컨트롤할 수 는 없지만 같이 제출의 용도를 정할 수 있다.

form : 이 속성은 양식 내에 있지 않더라도 포함하려는 요소의 id 속성 값을 사용한다.

name : 그룹과 관련된 이름이다.

~~~
figcaption
~~~
figure의 소자로써 부모의 내용의 나머지 설명 자막 또는 범례를 나타낸다.

ex)
<figure>
    <img src="ddfsfdsf" alt="ss">
    <figcaption>Elee</figcaption>
</figure>

~~~
figure
~~~
잠재적으로 소자, 그림, 캡션 및 내용은 단일 단위로 참조된다.
보통 하나의 이미지에 자막 혹은 제목이 있다고 생각하면 될것같음..


~~~

footer
~~~
단면 내용 또는 루트 절편 요소를 바닥글에 나타낸다

ex)
<article>
    <h1>dddd</h1>
        <ol>
            <li>dd</li> 
            <li>dd</li> 
            <li>dd</li> 
            <li>dd</li> 
        </ol>
    <footer>
        <p>오 예</p>
    </footer>
</article>
~~~
form
~~~
웹 서버에 정보를 제출하기위한 대화형 컨트롤이 포함된 문서 섹션을 나타낸다

ex)
<form action="" method="get" class="form-study"></form>


속성

action : 양식 정보를 처리하는 프로그램의 URI이다. 이 속성, 이 값은 formaction속성으로 재정의 할 수 있다.

autocomplete : 자동 완성 on off

enctype : method가 "post"이면 서버에 양식을 제출하는 데 사용되는 컨텐츠의 MIME 유형이다.

method : HTTP의 브라우저가 양식을 제출하는 방법
            GET : HTTP GET 메서드다. action URI에 '?'와 함께 추가된다. 구분 기호로 사용되며 결과는 URI는 서버로 전송된다. 양식에 부작용이 없고 아스키 코드만 되있으면 이거 써라.~
            POST : HTTP POST 메서드다. 양식 데이터는 양식 본문(body)에 포함되어 서버로 전송한다.
            DIALOG : 양식이 DIALOG일 때만 사용하자.

target : 위에 타겟 속성과 같음 iframe빼고
            iframename : 응답이 이름으로 표시된다.<iframe>

~~~
head
~~~
기계가 읽을 수 있는 정보 (문서에 대한 메타 데이터), 제목, 스크립트 및 스타일 시트를 담고있다.
~~~
header
~~~
일반적으로 입문 내용, 소개 등등 일반적으로 그룹을 나타낸다. 
제목뿐만 아니라 로고, 검색 양식, 저자 이름 및 기타 요소도 포함할 수 있다.
~~~
html
~~~
트리 구조의 최상위 root다.
다른 모든 요소의 부모이다. 루트 요소이며
~~~
hr
~~~
주제 단락 수준 요소 사이의 휴식 줄을 나타내준다. 
이야기 장면의 변화 또는 섹션 내 주제의 변화의 용도로 쓴다.

<hr>
~~~
wbr
~~~
브라우저가 선택적으로 줄을 뚫어 넘을 것 같은 애들일 때 써줌
문자가 텍스트 크기를 넘을 것 같으면 줄바꿈을 해주는 태그임~

걍 단어 사이에 <wbr>을 껴넣음
~~~
video
~~~
HTMLMediaElement API와 함께 사용하자.

비디오관련 내용 태그임 비디오의 소스를 넣어주면 비디오 볼 수 있음
~~~
var
~~~
시작 태그 종료 태그가 필수다

수학 표현식 같은 단어 사이에 쓴다.
사용하면 굵게 + 기울임체로 쓴다.
~~~
ul
~~~
순서화된 리스트 목록을 나타낸다
~~~
ol
~~~
순서가 없는 리스트 목록을 나타낸다
~~~
li
~~~
리스트 목록의 항목을 나타낸다
~~~
table
~~~
테이블 데이터를 나타낸다. 
순서가 있다.
    선택적 <caption> (테이블 밖에 제목)
    0개 이상의 <colgroup> (열 그룹)
    선택적 <thead> (테이블의 머리부분)
    다음 중 하나
        0개 이상의 <tbody> (테이블의 바디부분)
        하나 이상의 <tr> (테이블 행)
    선택적 <tfoot> (테이블의 바닥부분)

세트로 td(셀) ,th(제목 셀)도 있다.
~~~

script
~~~
외부 스크립트 파일을 사용할때 쓰는 태그임
~~~
link
~~~
외부 스타일 시트를 사용할 때 쓰는 태그임
~~~
img
~~~
이미지 파일을 사용하고 싶을 때 쓰는 태그임
~~~
input
~~~
클라이언트에게 데이터를 받으려고 웹 기반 형태의 대화형 컨트롤을 만드는데 사용한다
~~~
kbd
~~~
키보드,음성 입력 또는 기타 텍스트 입력 장치로부터의 사용자의 텍스트 입력을 나타내는 인라인 텍스트 범위를 나타냄
위의 요소 표현할 때 쓰는 거임

ex) <kbd>ctrl</kbd>이런식
~~~
label
~~~
input의 caption으로 사용한다. 인풋태그와 같이쓰는 제목?이라하긴 애매하고 암튼 그런 느낌
~~~
legend
~~~
부모 항목의 캡션을 나타낸다
대표적으로 fieldset의 캡션으로 자주 쓰임
~~~
main
~~~
main 태그의 content는 고유해야한다. 즉 반복되는 컨텐츠면 안되는거지.
잘 모르겠음
~~~
map
~~~
도형 a area를 정의하는 요소임
~~~
mark
~~~
텍스트를 표시와 강조를 해줌으로써 바깥 상황에서 표시된 경로의 관련성과 중요성,참조 또는 표기 목적으로 사용한다.
구문 강조 목적으로는 쓰지말자 <span>을 쓰도록.
~~~

meta
~~~
메타 데이터를 담고있다.
메타 데이터에 못담는 애들을 위한 태그
title, script, link, base, style
~~~
meter
~~~
공지된 범위 내의 스칼라나 소수 값중 하나를 나타낸다
~~~
div
~~~
일반 컨테이너임 
내용을 그룹화 해서 css js사용을 도 움
~~~
dfn
~~~
정의되는 용어를 표현한다
우선순위 title, abbr, text
~~~
nav
~~~
탐색 링크 섹션을 표시한다. 일반적인 예는 메뉴,목차 및 색인이다.
~~~
noscript
~~~
스크립트가 현재 브라우저에서 해제되어 있는 경우 페이지에서 스크립트 유형을 지원하지 않는 경우
~~~
object
~~~
화상 중첩 검색 컨텍스트 또는 리소스로 처리할 수 있는 외부 자원, 플러그인에 의해 처리될 것을 나타냄.

ex) 
<object type="application/pdf"
        data="/media/examples/In-CC0.pdf"
        width="250"
        height="200">
</object>

속성

data : 유효한 URL로서 자원의 주소. 데이터(data) 및 유형(type) 중 하나 이상을 정의해야 한다.

form : 오브젝트 요소가 연관된 양식 요소(있는 경우) (양식 소유자) 속성 값은 <form>과 동일한 문서에서 요소의 ID여야 한다.

height : CSS 픽셀 단위로 표시되는 리소스의 높이입니다.

name : 유효한 브라우징 컨텍스트의 이름(HTML5)

type : data로 지정된 자원의 컨텐츠 유형. 데이터(data) 및 유형(type) 중 하나 이상을 정의해야 한다.

width : CSS 픽셀 단위의 표시 리소스 너비.

ex)
<object data="movie.swf"
        type="application/x-shockwave-flash"></object>

<object data="movie.swf" type="application/x-shockwave-flash">
        <param name="foo" value="bar">
</object>

~~~
iframe
~~~
틀을 만들어준다. 속안의 내용은 html, img등등 다양한게 올 수 있다.
~~~
optgroup
~~~
option 들의 묶음으로 label을 설정해주면 구분이 다른 optgroup과 구분이 명확해진다.

ex)
<select>
    <optgroup label="Group 1">
        <option>Option 1.1</option>
    </optgroup>
    <optgroup label="Group 2">
        <option>Option 2.1</option>
        <option>Option 2.2</option>
    </optgroup>
    <optgroup label="Group 3" disabled>
        <option>Option 3.1</option>
        <option>Option 3.2</option>
        <option>Option 3.3</option>
    </optgroup>
</select>
위의 코드를 보면 Disabled 속성 값을 지정해주면 선택이 제한된다.
~~~
option
~~~
부모 요소에 보통 <select>, <optgroup>, <datalist>가 온다.
보통 부모 요소의 항목을 정의하는데 사용된다.

ex)
<select id="pet-select">
    <option value="">--Please Choose An Option--</option>
    <option value="cat">--Please cat An Option--</option>
    <option value="hamster">--Please hamster An Option--</option>
    <option value="parrot">--Please parrot An Option--</option>
    <option value="spider">--Please spider An Option--</option>
</select>


속성

value : 보통 value 값을 지정해서 양식에 제출할 값을 정해준다.

label : 레이블로 텍스트를 지정해줄 수 있고 그냥 내용으로 텍스트를 지정해줄 수 있다.
~~~

p
~~~
문단을 정의해준다.
~~~

output
~~~
출력 소자 output은 사이트 또는 앱 계산 또는 사용자 액션의 결과를 넣을 수 있는 디바이스의 요소다.

속성

form

name : 양식 제출 시의 이름

for

ex)
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
    <input type="range" name="b" value="50" /> +
    <input type="number" name="a" value="10" /> =
    <output name="result">60</output>
</form>

위의 예제는 a와 b의 값에 따라서 output이 바뀐다.
내 생각에는 form의 oninput 속성과 set인 가봐;;
~~~

param
~~~
매개 변수를 정의하는 <object>요소이다.

name과 value로 지정함
~~~

picture
~~~
source와 img를 같이 선언해주는데
브라우저가 picture태그를 지원안하거나 소스와 일치하는 항목이 없으면 img요소의 URL이 나온다.

media 속성일 때

ex)
<picture>
    <source srcset="mdn-logo-wide.png" media="(min-width: 600px)">
    <img src="mdn-logo-narrow.png" alt="MDN">
</picture>


tip. source 태그의 속성
media : 이 속성 은 사용자 에이전트가 각 <source>요소에 대한 평가할 미디어 조건을 지정함
        미디어 조건이 false면 해당 <source>요소를 건너뛴다.

type : 이 속성은 리소스 URL에 대한 MIME 유형을 지정한다. 
       사용자가 지정하지 않으면 요소를 건너뛴다.

ex)
<picture>
    <source srcset="mdn-logo-wide.png" type="image/svg+xml)">
    <img src="mdn-logo-narrow.png" alt="MDN">
</picture>
~~~

pre
~~~
HTML 파일에 기록된대로 정확하게 제시하는 서식이 텍스트를 나타낸다.
텍스트는 일반적으로 잘..안쓰는? "모노 스페이스" 글꼴을 사용해 렌더링된다

보통 뭔가 신기한 이모티콘같이 만드는 그런거 키보드 단축키들로 만든 소모양 그런거 쓸 때 
감싸줌 이 태그를
~~~
progress
~~~
일반적으로 진행 막대로 표시해서 작업의 완료 진행 상황을 보여준다.

ex)

<progress id="file" max="100" value="70"> 70& </progress>

속성

max : 최댓값 기본값은 1

value : 값 보통 최댓값을 100으로 나눈게 각각의 진행률이 된다.
~~~
q
~~~
태그 속 내용이 짧은 인라인 인용임을 나타낸다.

ex)
<p>According to Mozilla's website,
    <q
    cite="https://www.mozilla.org/en-US/about/history/details/">Firefox 1.0
    was released in 2004 and became a big success.</q></p>
~~~

template
~~~
HTML을 유지하기위한 메커니즘이다.
자바 스크립트를 사용해서 런타임시 이후 인스턴스화 될 수 있는 경우 즉시 렌더링을 할 수 없다.

HTMLTemplateElement를 갖는 content 판독 전용 속성이며, DocumentFragment 템플릿을 나타내는 DOM 서브 트리를 포함한다.

ex)
<table id="producttable">
    <thead>
        <tr>
            <td>UPC_Code</td>
            <td>Product_Name</td>
        </tr>
    </thead>
    <tbody>
        <~여기다가 값을 넣는거야~>
    </tbody>
</table>

<template id="productrow">
    <tr>
        <td class="record"></td>
        <td></td>
    </tr>
</template>

이제 js로 저기다가 template친구를 넣는거지..
~~~
textarea
~~~
여러 줄 일반 텍스트 편집 컨트롤을 나타낸다.
검토 또는 피드백 양식에 대한 설명을 자유 형식 텍스트의 꽤 큰 비용을 입력할 수 있도록 할 경우에 쓴다.

<textarea id="story" name="story"
          rows="5" cols="33">
It was a dark and stormy nigth...
</textarea>

속성

cols,rows : 몇글자 몇줄인지 정할 수 있다.
~~~
time
~~~
특정 시간을 나타낼 때 사용한다.
datatime으로 날짜를 기계가 읽을 수 있는 형식으로 변환하는 속성을 포함해  검색 엔진 결과 또는 알람 같은 기능에 유요함

다음 중 하나를 사용할 수 있다.
    24시간 제로 시간
    그레고리력의 정확한 날짜
    유효한 시간

ex)
<time datetime="2018-07-07">July 7 </time>
<time datetime="20:00">20:00 </time>
<time datetime="PT2H30M">2h 30m</time>

날짜
24시간 시간
유효한 시간 순의 예제이다..

~~~
track
~~~
오디오와 비디오 요소의 자식 태그로 사용한다.
예로 자막을 자동으로 처리하거나 시간이 지정된 텍스트 트랙을 지정할 수 있다.
트랙의 형식은 WebVTT, TTML로 포맷된다.

ex)
<video controls width="250"
       src="/media/examples/friday.mp4">
    <track default kind="captions"
           srclang="en"
           src="/media/examples/friday.vtt"/>
</video>

~~~

rp
~~~
루비 주석의 표시를 지원하지 않는 브라우저를 위해 사용된다.

<rt>만 써도 잘 올라가는데 애를 쓰는 이유는 괄호를 제공하는데 쓰는 것이다.
왜냐 루비를 지원하지 않는 브라우저에서도 잘보여야되니까
잉 (ing) 기모링~ (gimoring~)이런 식으로 지원이 되는거지
그럼 루비를 지원하지 않아도 알아 볼 수가 있다.
~~~

rtc
~~~
rtc는 의미를 뜻한다.
루비에 표시 문자의 의미 <rb> 주석을 포용하며 ruby 내부에서 쓴다.

rbc 태그의 내용엔 rb, rt(발음), rp를 모두 쓸 수 있다.
rb 태그는 rt(발음), rtc(의미) 주석을 모두 쓸 수 있다.
~~~
ruby
~~~
한자를 위한 루비 주석이다.
~~~
s
~~~
s는 취소 선, 또는 그것을 통해서 선을 렌더링한다.
더 이상 관련이 없거나 더 이상 정확하지 않은 것을 나타낼 때 사용한다.
그러나 문서 편집 표시에는 적합하지 않다. del과 ins 요소가 더 나음

ex)
<p><s> There Will be a few tickets available at the box office tonight.</s></p>
~~~
samp
~~~
컴퓨터 프로그램의 샘플을 나타낸다. 인라인 텍스트(또는 인라인 인용) 출력을 감쌀 때 쓴다.

ex)
<p><samp>Keyboard not found Press F1 to continue</samp></p>
~~~
section
~~~
섹션에는 대게 제목이 있다.
HTML의 문서내에 포함된 독립 섹션을 나타낸다. 구체적인 의미론적 요소가없는..

<section>
    <h1>Introduction</h1>
    <p>People have been catching fish for food since before recorded history..</p>
</section>
~~~
select
~~~
<option> 메뉴를 제공하는 컨트롤을 나타낸다.

속성

label : 이 속성으로 선택하려는 곳의 항목의 이름을 설정해줄 수 있고

value : 이 속성으로 제출할 때의 값을 정해줄 수 있고.
~~~
slot
~~~
별도의 DOM 트리를 만들어서 slot들을 함께 만들 수 있다. 자신의 마크업으로 채울 수 있는 웹 구성 요소 내부에 자리한다.
ex)
<div class="attributes">
    <h4>Attributes</h4>
    <slot name="attributes"><p>None</p></slot>
</div>


~~~
small
~~~
보통 글씨가 확 작아지는데.
독립적인 저작권 및 법적 텍스트와 같은 측의 의견을 나타낼 때 글씨를 작게한다.

ex) <p><small>The content is licensed under a Creative Commons
Attribution-ShareAlike 2.5 Generic License.</small></p>
~~~
span
~~~
컨텐츠를 파싱하기 위한 제네릭 인라인 컨테이너다.
div와 비슷한 역할이지만. div는 블록 컨테이너임.
스타일링 목적으로 쓰거나 lang같은 속성을 공유하기 위해 요소를 그룹핑할 때 쓴다.

ex)
<p><span>Some text</span></p>
~~~
strong
~~~
글자에 강조 효과를 줄 때 사용한다. 글자가 굵어짐.
~~~
style
~~~
문서나 문서 일부에 대한 스타일 정보를 포함한다.
개인적으로 외부 스타일 시트만 쓰는 것 같음. 관리하기 편하고 의존성을 낮춰주니까.
~~~
sub
~~~
인쇄상의 이유로 낮고 작게 표시되는 텍스트의 범위를 표시한다.
스타일링 용도로 사용 X

ex)
<p>The Chemical Formula Of Water Is H<sub>2</sub>O</p>
~~~
sup
~~~
인쇄상의 이유로 첨자로 표시하는 인라인 텍스트를 지정한다.
스타일링 용도로 사용 X

ex)
<p>a<sup>2</sup></p>
~~~
summary
~~~
<details>태그의 자식 요소이며
요약,캡션,또는 legend 지정의 역할을 한다.

ex)
<details>
    <summary>I have keys but no doors.</summary>
    A... <--- 요약되있는 걸 눌러보면 이게 뜸 다시 눌러서 요약시킬 수 있음
</details>
~~~

source
~~~
여러 미디어에 대한 지정을 한다. <picture>, <audio>, <video> 등등

ex)
<video controls
       width="250"
       height="200"
       muted>
       <source src="/media/examples/flower.webm"
               type="video/webm">
       <source src="/media/examples/flower.mp4"
               type="video.mp4">
        SSSSSSSSSDFASD
</video>

속성

media : <picture>태그에서만 사용해야 한다.

src : <audio>, <video>에서 필요하다. source요소가 picture 요소안에 있으면 이 속성의 값은 무시된다.

srcset : 브라우저가 사용할 소스로 표시되는 가능한 이미지 세트를 나타내는 쉼표로 구분된
         하나 이상의 문자열 목록이다. 각 문자열은 다음으로 구성된다.
            1. 이미지에 대한 하나의 URL
            2. 너비 설명자 'w' 바로 다음에 오는 양의 정수. 누락된 경우 기본값은 무한
            3. 픽셀 밀도 설명자 'x' 누락된 경우 기본값은 1x입니다.

이 srcset 속성은 picture요소의 source요소가 직접적인 자식일 때 효과가 있다.
~~~



