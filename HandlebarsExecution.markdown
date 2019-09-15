Execution(실행)
작은 Templates 만들어보기.
~~~
컨텍스트와 함께 템플릿을 실행해 핸들바 템플릿을 평가한 HTML 결과를 가져온다.

var context = {title: "My New Post", body: "This is my first post!"};
var html = template(context);

결과는

<div class="entry">
    <h1>My New Post</h1>    
    <div class="body">
        This is my first post!
    </div>
</div>

이렇게 된다.
~~~
Options
~~~
템플릿 함수는 옵션 객체를 두 번째 매개 변수로 전달해 사용자 정의할 수 있다.

아 그래서 Helper에 항상 옵션이 두 번째 매개 변수로 전달되있던거구나.

Data는 사용자 정의 @variable 개인 변수를 정의하기 위해 객체를 전달한다.


Helper는 세계적으로 정의된 헬퍼 외에도 사용자 정의 헬퍼를 제공한다.
이 개체(Helper)에 정의된 값은 템플릿 실행기간동안 전역 개체에 정의된 모든 값을 대체한다.
즉 우선 순위가 1등이된다 이건가?


Partials은 전역적으로 정의된 부분 외에도 사용자 지정 부분을 제공하려면 전달해라~
이 개체(Partials)에 정의된 값은 템플릿 실행 기간 동안 전역 개체에 정의된 모든 값을 대체한다.
~~~

