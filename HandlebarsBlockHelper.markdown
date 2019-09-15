Block 표현식
~~~
블록 표현식을 사용하면 현재와 다른 컨텍스트를 사용해 템플릿 섹션을 호출할 헬퍼를 정의할 수 있다.
이 블록 헬퍼는 #뒤에 헬퍼 이름으로 식별되며 동일한 이름으로 /뒤에 닫힌 콧수염이 필요하다.
~~~

Basic Blocks(기본 블록)
~~~
데모 목적으로 Helper가 없는 것처럼 블록을 호출하는 블록 Helper를 정의해보자(예제 1)

<div class="entry">
    <h1>{{title}}</h1>
    <div class="body">
        {{#noop}}{{body}}{{/noop}}
    </div>
</div>

noop Helper는 no operation의 약자이다.
noop Helper는 options hash를 받는다.
options hash는 일반 컴파일된 핸들바 템플릿처럼 동작하는 함수(options.fn)를 포함한다.
특히 그 함수는 컨텍스트를 가져와서 문자열을 반환한다.

Handlebars.registerHelper('noop', function(options) {
    return options.fn(this);
});

위의 예제에서 컨텍스트 객체의 noop 필드는 다음을 사용해 참조된다.
{{./noop}}


핸들바는 항상 현재 컨텍스트로 Helper를 호출하므로 현재 컨텍스트에서 블록을 평가하기 위해 사용해 블록 호출
이런 방식으로 정의된 Helper는 컨텍스트에 정의된 field보다 우선시된다.
Helper가 마스킹한 field에 액세스하기 위해서 경로 참조를 사용할 수 있다.
~~~
Basic Block Variation
~~~
구문(syntax)를 더 잘 설명하기 위해 줄 바꿈된 텍스트에 마크 업을 추가하는 다른 블록 Helper 정의 (예제 2)

<div class="entry">
    <h1>{{title}}</h1>
    <div class="body">
        {{#bold}}{{body}}{{/bold}}
    </div>
</div>


이 bold Helper는 텍스트를 굵게 표시하기 위해 마크업을 추가한다 <bold></bold> 마크업 추가
(예제 1)과 마찬가지로 함수는 컨텍스트를 입력으로 받아 String으로 반환한다.

Handlebars.registerHelper('bold', function(options) {
    return new Handlebars.SafeString(
        '<div class="mybold">'
        + options.fn(this)
        + '</div>');
});
~~~
The [with] Helper 
~~~
with Helper는 Helper에 매개 변수를 전달하는 방법을 보여준다.
Helper가 매개 변수와 함께 호출되면 템플릿이 전달된 컨텍스트와 상관없이 호출된다.

<div class="entry">
    <h1>{{title}}</h1>
    {{#with story}}
        <div class="intro">{{{intro}}}</div>
        <div class="body">{{{body}}}</div>
    {{/with}}
</div>

with Helper는 JSON 객체의 섹션에 중첩된 속성이 포함되어 있고 부모 이름을
반복하지 않으려는 경우 유용하다.

with Helper를 구현하려는 것은 noop Helper를 구현하는 것과 매우 비슷하다.
Helper는 매개 변수를 사용할 수 있으며 매개 변수는 {{mustache}}블록 내에서 직접 사용되는 식과 같이 평가된다.

Handlebars.registerHelper('with', function(context, options) {
    return options.fn(context);
});

매개 변수는 전달된 순서대로 옵션 해쉬에 의해 참조된다.

보니까 바로 with story(매개변수)를 쓰면 바로 with Helper안의 내용들은 story.{내용}으로
바로 인식이 되는 것 같음.ㅇㅇ;;

~~~

Simple Iterators(간단한 반복자)
~~~
핸들바 내장 Helper는 일반 핸들바 블록 Helper로 정의된다.

내장 Helper의 작동 방식을 살펴보자 (예제3)

<div class="entry">
    <h1>{{title}}</h1>
    {{#with story}}
        <div class ="intro">{{{intro}}}</div>
        <div class ="body">{{{body}}}</div>
    {{/with}}
</div>
<div class="comments">
    {{#each comments}}
        <div class="comment">
            <h2>{{subject}}</h2>
            {{{body}}}
        </div>
    {{/each}}
</div>

with는 이미 말했고

이 경우(each)에는 주석(each) 배열(context)의 각 요소마다 한번에 전달된 블록을 호출하려한다.

Handlebars.registerHelper('each', function(context, options) {
    var ret = "";
    
    for(var i=0, j=context.length; i<j; i++) {
        ret = ret + options.fn(context[i]);
    }

    return ret;
});

결국 위의 식을 해석해보면 comments의 context[i]일때의 subject,body값들을 i<j랑 같아질 때 까지 계속 반복하는거지
결국 <div>속 subject가 여러개 생기고 한번에 출력이 된다.

list 패턴은 고급 반복자를 만들 때 쓰인다.

{{#list nav}}
    <a href="{{url}}">{{title}}></a>
{{/list}}

이 Helper는 each Helper와 유사하다.

Handlebars.resgisterHelper('list', function(context, options) {
    var ret = "<ul>";

    for(var i=0, j=context.length; i<j; i++) {
        ret = ret + "<li>" + options.fn(context[i]) + "</li>";
    }

    return ret + "</ul>";
});

암튼 위의 방식으로도 Helper를 쓸 수 있다.

underscore.js 또는 SproutCore의 런타임 라이브러리와 같은 라이브러리를 사용하면 좀 더 이쁘게 만들 수 있긴 함

~~~
Conditionals(조건)
~~~
블록 Helper의 또 다른 일반적인 사용 사례는 조건문을 평가하는 것이다.
반복자와 마찬가지로, 핸들바의 내장 if 및 if 컨트롤 구조는 일반적인 핸들바 Helper로 구현된다.

{{#if isActive}}
    <img src="star.gif" alt="Active">
{{/if}}

컨트롤 구조는 일반적으로 현재 컨텍스트를 변경하지 않고 대신 일부 변수를 기반으로 블록을 호출할 지
여부를 결정한다.

Handlebars.registerHelper('if', fucction(conditional, options) {
    if(conditional) {
        return options.fn(this);
    }
});

조건이 트루면 noop Helper와 똑같은걸 실행하네

조건이 거짓일 때 Helper에 삽입해야하는 경우에

{{#if isActive}}
    <img src="star.gif" alt="Acitve">
{{else}}
    <img src="cry.gif" alt="Inactive">
{{/if}}

if안에 else를 삽입한다. else아래 내용은 거짓일 때 Helper에 넣어줄 내용이다.

handlebars는 else가 보이면 그 블록에 대해서 options.inverse를 제공한다

Handlebars.registerHelper('if', function(conditional, options) {
    if(conditional) {
        return options.fn(this);
    } else {
        return options.inverse(this);
    }
});

Handlebars는 Helper를 options.hash 속성으로 연결해 Block Helper를 위한 추가 메타 데이터를 제공한다.

응용해서
{{else}}에 후속 도우미 호출을 포함시켜서 조건을 연결할 수 도 있다.(else if)된다는 소리인듯.

{{#if isActive}}
    <img src="star.gif" alt="Active">
{{else if isInactive}}
    <img src="cry.gif" alt="Inactive">
{{/if}}

후속 호출에서 동일한 Helper를 사용할 필요는 없다. (unless Helper)를 쓰면 else 부분을 쓸 수 있다.
Helper의 값이 다르면 닫는 }}이 여는 Helper 이름과 일치해야 한다.

즉 if와 else if else, unless 등등을 알아보았다.
~~~
Hash Arguments(hash 인자)
~~~
일반 Helper와 마찬가지로 블록 Helper는 options.hash를 최종 인수로 받아들 일 수 있다.
위의 (예제 3)으로 가서 우리가 만들 <ul> 요소에 여러 개의 선택적 속성을 추가할 수 있게 하자.

{{#list nav id="nav-bar" class="top"}}
    <a href="{{url}}">{{title}}</a>
{{/list}}

handlebars는 최종 hash를 options.hash로 제공한다.
이를 통해서 가변 매개변수를 더 쉽게 수용할 수 있으며 hash(선택 사항)도 허용한다.
템플릿이 hash 인수를 제공하지 않으면 handlebars는 빈 객체({})를 자동으로 전달한다.
고로 hash 인수가 있는지 없는지 확인할 필요는 없다.

Handlebars.registerHelper('list', function(context, options) {
    var attrs = Object.keys(options.hash).map(function(key) {
        return key + '="' + options.hash[key] + '"';
}).join(" ");

    return "<ul " + attrs + ">" + context.map(function(item) {
        return "<li>" + options.fn(item) + "</li>";
    }).join("\n") + "</ul>";
});  

hash 인수는 위치 인수로 인한 복잡성없이 여러 가지 선택적 매개변수를 블록 Helper에 제공할 수 있는
강력한 방법을 제공한다.

블록 Helper는 개인 변수를 자식 템플릿에 삽입할 수 도 있다.
원본 컨텍스트 데이터에 없는 추가 정보를 추가하는데 유용하다.

예를 들어서 목록을 반복할 때 현재 인덱스을 개인 변수로 제공할 수 있다.(예제4)

{{#list array}}
    {{@index}}. {{title}}
{{/list}}

Handlebars.registerHelper('list', function(context, options) {
    var out = "<ul>", data;
    
    if (options.data) {
        data = Handlebars.createFrame(options.data);
    }

    for (var i=0; i<context.length; i++) {
        if (data) {
            data.index = i;
        }

        out += "<li>" + options.fn(context[i], { data: data}) + "</li>";
    }

    out += "</ul>";
    return out;
}); 

data 옵션을 통해 제공된 개인 변수는 모든 하위 범위에서 사용할 수 있다.

부모 범위에 정의된 개인 변수는 경로 쿼리르 통해 액세스할 수 있다.
부모 반복자(iterator)에 인덱스 필드에 액세스하기 위해서 @../index를 사용할 수 있다.

자체 데이터를 할당하는 각 도우미에서 새 데이터 프레임을 작성하십쇼.
안그러면 다운 스트림 Helper가 의도치 않게 업스트림 변수를 변경시킬 수 있다.

기존 데이터 개체와 상호 작용하기 전에 데이터 필드가 정의되어 있는지 확인하라.
전용 변수 동작은 조건부로 컴파일되며 일부  템플릿은 이 필드를 생성안 할 수도 있다.
~~~
Block Parameters
~~~
지원 헬퍼로 부터 명명된 매개 변수를 받을 수 있다.

{{#each users as luser userId|}}
    ID: {{userId}} Name: {{user.name}}
{{/each}}

위의 특정 (예제 5)에서 사용자는 현재 컨텍스트와 동일한 값을 가지며 userId는 반복에 대한 인덱스 값을 가진다.
이를 통해 중첩된 헬퍼는 개인 변수에서 발생할 수 있는 name 충돌을 피할수 있다.

{{#each users as luser userId|}}
    {{#each user.book as |book bookId|}}
        User Id: {{userId}} Book Id: {{bookId}}
    {{/each}}
{{/each}}

여기 잘 이해가 안감;;

Handlebars.registerHelper('block-params', function() {
    var args = [],
        option = arguments[arguments.length - 1];
    for (var i = 0; i < arguments.length - 1; i++) {
        args.push(arguments[i]);
    }

    return options.fn(this, {data : options.data, blockParams: args});
});

{{#block-params 1 2 3 as |foo bar baz|}}
    {{foo}} {{bar}} {{baz}}
{{/block-params}}

다수의 내장 헬퍼가 블록 매개 변수를 지원하며 모든 사용자 정의 헬퍼는
blockParams(block-params) 옵션 필드를 통해 제공할 수 있다.
options.fn.blockParams field를 통해서 템플릿이 참조하는 블록 매개변수 수를 결정한다.
이 정해진 수를 초과하면 매개 변수는 참조되지 않는다.
나는 가독성을 위해서 헬퍼를 생략하지는 않을 것이다..


~~~

Raw Blocks
~~~
처리되지 않은 mustache 블록을 처리해야하는 템플릿에 원시 블록을 사용한다
{{{{raw-helper}}}}
    {{bar}}
{{{{/raw-helper}}}}

내용의 간섭없이 raw-helper가 실행될 것이다. 
아래 함수를 보면 걍 options.fn();을 반환하는거 보니 ㄹㅇ 내용은 상관없이 raw-helper 실행시키네


Handlebars.registerHelper('raw-helper', function(options) {
    return options.fn();
});

{{bar}}를 렌더링할 것이다.
~~~


