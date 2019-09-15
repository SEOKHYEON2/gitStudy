Handlebars.compile
~~~
JS로 템플릿을 컴파일하려면 Handlebars.compile을 사용하면 된다.

var source = document.getElementById("entry-template").innerHTML;
var template = Handlebars.compile(source);

이 방법은 프로덕션 응용 프로그램에서는 권장되지 않는다.
더 좋은 방법은 템플릿을 미리 컴파일하는 것이다.
이로 인해서 필요한 런타임 라이브러리가 줄어들고 브라우저에서 템플릿을 compile하지 않아도 크게 절약된다.
이것은 모바일 장치로 작업할 때 중요한 사항이다.

긍까 템플릿을 미리 컴파일하는게 좋다는 거지~
~~~

handlebar precompiler
~~~
npm install handlebars -g   //핸들바를 먼저 깔아주고~ -g를 붙이면 어느 프로젝트에서도 쓸 수 있음

이제 precompiler를 쓸 준비가 된거야~

handlebars <input> -f <output>

컴파일러는 템플릿을 Handlebars.templates에 삽입한다.
입력 파일(input)이 person.handlebars인 경우 컴파일러는
Handlebars.templates.person에 파일을 삽입한다.
즉.. 이 템플릿은 로컬에서 컴파일이된 템플릿과 같은 방식으로 직접 실행될 수 있다.

그러면 Handlebars.templates.person(context, options);
이런 식으로 되겠지 ㅇㅇ;;

긍까 컴파일을 여기서 할수있다는거네


(성능 상승 방법)

사전에 컴파일된 템플릿으로 작업하는 경우 이걸 사용할 필요는 없어.
하지만? 더 작은 "runtime"빌드는 사용할 수 있어
<script src="/libs/handlebars.runtime.js"></script>
핸들바에서 컴파일하는게 가장 비용이 크다.
다운로드 크기를 줄이는 것 외에도 클라이언트 측 컴파일을 제거하면 부팅 시간이 크게 단축되겠지?!
~~~
Optimizations(최적화)
~~~
템플릿을 사전 컴파일 하고 있으므로 컴파일러에 여러 최적화를 적용할 수 있다.
첫번째는 알려진 헬퍼 목록을 컴파일러에 지정할 수 있다.

handlebars <input> -f <output> -k each -k if -k unless
-k = -knownOnly

Handlebars 컴파일러는 성능을 위해 해당 헬퍼에 대한 엑세스를 최적화한다.
컴파일시에 모든 헬퍼가 알려지면(-k) -k 옵션은 가장 빠른 실행을 제공하는 가장 작은 생성 코드를 제공함.

즉 모두 알려진 헬퍼 목록으로 지정해주면 빨라진다 이거네
~~~

Usage
~~~
Usage: node ./bin/handlebars [template|directory]...

Options:
  -f, --output         Output File
  --map                Source Map File                                                    [string]  [default: undefined]
  -a, --amd            Exports amd style (require.js)
  -c, --commonjs       Exports CommonJS style, path to Handlebars module                                 [default: null]
  -h, --handlebarPath  Path to handlebar.js (only valid for amd-style)                                     [default: ""]
  -k, --known          Known helpers
  -o, --knownOnly      Known helpers only
  -m, --min            Minimize output
  -n, --namespace      Template namespace                                              [default: "Handlebars.templates"]
  -s, --simple         Output template function only.
  -N, --name           Name of passed string templates. Optional if running in a simple mode. Required when operating
                       on multiple templates.
  -i, --string         Generates a template from the passed CLI argument.
                       "-" is treated as a special value and causes stdin to be read for the template value.
  -r, --root           Template root. Base value that will be stripped from template names.
  -p, --partial        Compiling a partial template
  -d, --data           Include data when compiling
  -e, --extension      Template extension.                                                       [default: "handlebars"]
  -b, --bom            Removes the BOM (Byte Order Mark) from the beginning of the templates.
  -v, --version        Prints the current compiler version
  --help               Outputs this message
~~~
~~~
위의 것은 handlebars의 옵션인듯

만약 프리 컴파일러의 일반 모드를 사용하는 경우 
그 결과인 템플릿은 상대 템플릿 이름으로 확장명을 사용하며 Handlebars.templates 객체에 저장된다.
이러한 템플릿은 템플릿과 동일한 방식으로 실행될 수 있다.

만약 단순 모드를 사용한 경우 사전 컴파일러는 단일 JS 메서드를 사용해야 한다.
이 단일 JS 메서드를 실행하려면 Handlebars.template 메서드로 전달되어야하며
결과 오브젝트가 정상적으로 사용될 수 있다.
~~~

NodeJS에서 템플릿 사전 컴파일링하기
~~~
이건 안봐도 될듯
지금 내 상황에는 ㅇㅇ;;
~~~



