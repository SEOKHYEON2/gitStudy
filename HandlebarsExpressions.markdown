기본 사용법
~~~
<h1> {{title}}</h1>
이 표현식은 "현재 컨텍스트에서 title속성을 찾는다"를 의미한다.

실제로는 title 이름의 Helper를 찾은 다음 위의 작업을 수행하는 것을 의미한다.


.으로 구분된 경로일 때도 있다.

<h1>{{article.title}}</h1>
이 표현식은 "현재 컨텍스트에서 article속성을 찾은 다음 결과에서 title 속성을 찾는다"를 의미한다.

같은 표현식으로 
<h1>{{article/title}}</h1>도 가능하다. handlebars는 /를 지원한다.

유효한 식별자가 아닌 속성을 참조하기 위해 세그먼트 리터럴 표기법 [] 을 사용할 수 있다.

{{#each articles. [10]. [# comments]}}
    <h1> {{subject}} </h1> //현재 컨텍스트에서 subject속성을 찾는다.
    <div> 
        {{body}} //현재 컨텍스트에서 body속성을 찾는다.
    </div>
{{/each}}

JS 스타일의 문자열 "과 '도 사용할 수 있다.

{{{foo}}} 핸들바가 값을 이스케이프하지 않게하려면 {{{ }}}을 사용해야 한다.
~~~
헬퍼(Helper)
~~~
헬퍼 호출은 간단한 식별자이며 0개 이상의 매개 변수(공백으로 구분한다.)가 뒤에 온다.
각 매개변수는 Handlebars 표현식이다.
{{{link story}}}

이말인 즉슨 link Helper이며 story라는 link Helper의 매개 변수이다.

예를 들어보자면
{{{link "See more..." story.url}}} //링크 헬퍼의 "See more...", story.url 매개 변수

Handlebars.registerHelper('link', function(text, url){
    url = Handlebars.escapeExpression(url);
    text = Handlebars.escapeExpression(text);
    
    return new Handlebars.SafeString(
        "<a href='" + url + "'>" + text + "</a>"
    );
});

이걸 보면 어떻게 되냐면 <a href='story.url'>See more</a> 이렇게 되는 것이지
~~~
하위 표현식(inner-helper를 outer-helper의 매개 변수로 사용할 수 있다.)
~~~
핸들 바는 하위 표현식을 지원해 단일 {}내에서 여러 헬퍼를 호출해 내부 헬퍼 호출 결과를
외부 헬퍼에 대한 인수로 전달할 수 있다. 하위 표현식은 괄호로 구분된다.

{{outer-helper (inner-helper 'abc') 'def'}}

이 표현식은 inner-helper는 호출될것이다. 문자열 인자 'abc'를 사용해 호출되며 
inner-helper 함수가 반환하는 모든 내용은 첫 번째 인수로 outer-helper에 전달된다.
(그리고 'def'는 두 번째로 전달된다) 
~~~

공백 제어
~~~

{{~}}로 문자를 추가해 콧수염 문장의 양쪽에서 템플릿 공백을 생략할 수 있다.
해당 측면의 모든 공백은 첫 번째 핸들 바 표현식 또는 해당 측면의 공백이 아닌 문자까지 제거된다.

ex) ~를 사용한 경우
{{#each nav ~}}
    <a href="{{url}}">
        {{~#if test}}
            {{~title}}
        {{~^~}}
            Empty
        {{~/if~}}
    </a>
{{~/each}}

결과
<a href="foo">bar</a><a href="bar">Empty</a>
보다 시피 공백이 없다...

ex) ~를 사용하지 않은 경우

{{#each nav }}
    <a href="{{url}}">
        {{#if test}}
            {{title}}
        {{^}}
            Empty
        {{/if}}
    </a>
{{/each}}

결과
<a href="foo">
    bar
</a>
<a href="bar">
    Empty
</a>
보다 시피.. 공백이 많다 차이는 명확하다잉
~~~
Escaping
~~~
두가지 방법이 있다.
1.  \{{escaped}}
2.  {{{{raw}}}}
      {{escaped}}
    {{{{/raw}}}}

