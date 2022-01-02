### Printing Constants and Variables

You can print the current value of a constant or variable with the `print(_:separator:terminator:)` function:

상수 또는 변수의 현재 값을 출력할 수 있다 키워드 함수를 통해서



The `print(_:separator:terminator:)` function is a global function that prints one or more values to an appropriate output. 

프린트 함수는 글로벌 함수이며 하나 또는 여러 값을 적절한 아웃풋으로 출력한다.



In Xcode, for example, the `print(_:separator:terminator:)` function prints its output in Xcode’s “console” pane

예를 들어 엑스코드에서 함수는 출력한다 출력을 엑스코드 콘솔 창에



The `separator` and `terminator` parameter have default values, so you can omit them when you call this function.

두가지 키워드는 기본 값을 갖는다 그래서 우리는 해당 함수를 부를때 생략할 수 있다.



By default, the function terminates the line it prints by adding a line break.

기본적으로 함수는 종료한다 그 줄을, 이 함수는 라인 브레이크를 추가하며 출력한다.



To print a value without a line break after it, pass an empty string as the terminator

라인 브레이크 없이 값을 출력하고 싶다면 터미네이터에 빈 스트링을 전단하세요



For example, `print(someValue, terminator: "")`.

예를 들어서 키워드와 같이



For information about parameters with default values, see [Default Parameter Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID169).

기본 값 파라미터에 대해서 궁금하다면 링크를 참고하세요.



Swift uses *string interpolation* to include the name of a constant or variable as a placeholder in a longer string, and to prompt Swift to replace it with the current value of that constant or variable.  ????

스위프트는 문자열 보간을 사용한다 상수의 이름 또는 긴 문자열안 플레이스 홀덜로서 변수를 포함시키기 위해 그리고 스위프트를 자극하기 위해서 이것을 대체한다 상수 또는 변수의 현재 값을





Wrap the name in parentheses and escape it with a backslash before the opening parenthesis: ????



All options you can use with string interpolation are described in [String Interpolation](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html#ID292).

문자열 보간과 관련된 모든 옵션은 해당 링크에 있습니다.



appropriate: 적합한

pane: 창유리, 평면

terminator: 터미네이터??

string interpolation: 문자열 보간

prompt: 즉석의 즉각적인, 자극하다 생각나게 하다

parenthesis: 괄호