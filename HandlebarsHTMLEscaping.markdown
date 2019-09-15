HTML Escaping
~~~
핸들바가 값을 escape하는 것을 원치 않는다면 {{{contents}}}를 써라~

<div class="entry">
    <h1>{{title}}</h1>
    <div class="body">
        {{{body}}}
    </div>
</div>

아래 내용과 함께 쓰면

{
    title: "All about <p> Tags",
    body: "<p>This is a post about &lt;p&gt; tags</p>"
}

결과는 아래 처럼 된다.

<div class="entry">
    <h1>All about &lt;p&gt; Tags</h1>
    <div class="body">
        <p>This is a post about &lt;p&gt; tags</p>
    </div>
</div>

위의 차이를 보면 알겠지만 {{{}}}을 써준 곳은 태그가 간접표현식으로 안바뀌고 있는 그대로 나오는데
{{}}을 써준 title을 보면 태그가 간접표현식으로 바껴서 나온다 ㄷㄷ;;

핸들바는 (Handlebars.SafeString)을 이스케이프하지 않는다.
자체 HTML을 생성하는 헬퍼를 작성하는 경우 일반적으로 
새 Handlebars.SafeString(result)을 반환하려고한다.
이러한 상황에서는 매개변수를 수동으로 이스케이프 처리하려고 한다.

Handlebars.registerHelper('link', function(text, url) {
    text = Handlebars.Utils.escapeExpression(text);
    url = Handlebars.Utils.escapeExpression(url);

    var result = '<a href="' + url + '">' + text + '</a>';

    return new Handlebars.SafeString(result);
});

전달된 매개변수는 escape되지만 응답을 안전한게 표시하므로 {{{}}}을 안써도 핸들바는 
마크를 escape하려고 하지않는다. 마크가 뭐지?
아마도 SafeString을 쓰면 반환 값이 escape되지 않는다 이런 것같음 안전하게 내보내는 것이라서.
~~~



