Handlebars Paths
~~~
핸들바는 간단한 경로를 지원한다. mustache 처럼
<p>{{name}}</p>

핸들바는 중첩 경로를 지원하므로 현재 컨텍스트 아래에 중첩된 속성을 조회할 수 있다.

<div class="entry">
    <h1>{{title}}</h1>
    <h2>By {{author.name}}</h2>

    <div class="body">
        {{body}}
    </div>
</div>

이 템플릿과 아래 context가 만나면?
var context = {
    title: "My First Blog Post!",
    author: {
    id: 47,
    name: "Yehuda Katz"
    },
    body: "My first post. Wheeee!"
};

결과는
<div class="entry">
    <h1>My First Blog Post!</h1>
    <h2>By Yehuda Katz</h2>
    
    <div class="body">
        My first post. wheeee!
    </div>
</div>
이렇게 될것이다.

이 처럼 많은 원시 JSON 객체들이 핸들바 템플릿을 사용할 수 있다.

중첩된 핸들바 경로엔 ../ 세그먼트가 포함될 수 있으며, 이는 부모 컨텍스트에 대한 경로를 평가한다.

<h1>Comments</h1>

<div id="comments">
    {{#each comments}}
    <h2><a href="/posts/{{../permalink}}#{{id}}">{{title}}</a></h2>
    <div>{{body}}</div>
    {{/each}}
</div>

comment 컨텍스트에서 링크가 조회되더라도 여전히 기본 컨텍스트(게시물)로 돌아가서 
영구 링크를 검색할 수 있다.

../가 해결하는 정확한 값은 블록을 호출하는 Helper에 따라 다릅니다. ../를 사용하면 
컨텍스트가 변경될 때만 필요하므로 each같은 Helper의 자식은 ../를 사용해야하지만
그렇지않은 Helper의 자식은 사용하지말자잉~..


{{permalink}}
{{#each comments}}
    {{../permalink}}

    {{#if title}}
        {{../permalink}}
    {{/if}}
{{/each}}

이 예에서, ../permalink 참조의 모든 것은 비록 상이한 블록 내에 위치하더라도 동일한 
퍼머링크 값을 참조한다.

또 핸들바는 다음 참조를 통해 Helper와 데이터 필드 사이의 name 충돌 해결을 허용한다.

<p>{{./name}} or {{this/name}} or {{this.name}}</p>
겹칠 것 같으면 위의 3가지 방법을 섞어쓰면 된다 이건가?!

위의 어떤 것도 현재 컨텍스트의 이름 필드가 같은 이름의 Helper가 아니게끔 사용되도록 한다.
~~~
Template comments with {{!-- --}} or {{! }}.
~~~
핸들바에서도 주석을 사용할 수 있다.

<div class="entry">
    {{!-- only output author name if an author exists --}}
    {{#if author}}
        <h1>{{author.firstName}} {{author.lastName}}</h1>
    {{/if}}
</div>

주석은 결과 출력에 포함되지 않는다. 의견을 표시하려면 html 주석만 사용하면 출력된다. 아래처럼

<div class="entry">
    {{! This comment will not be in the output }}
    <!-- This comment will be in the output -->
</div>

{{}} 이나 다른 핸들바 토큰을 포함해야하는 주석은 {{!-- --}} 주석을 사용해야 된다.
~~~
Helper
~~~
핸들바 헬퍼는 템플릿의 모든 컨텍스트에 액세스할 수 있다.
Handlebars.registerHelper 메서드로 헬퍼를 등록할 수 있다.

<div class="post">
    <h1>By {{fullName author}}</h1>
    <div class="body">{{body}}</div>

    <h1>Comments</h1>

    {{





