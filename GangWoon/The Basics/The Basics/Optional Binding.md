### Optional Binding

You use *optional binding* to find out whether an optional contains a value, and if so, to make that value available as a temporary constant or variable. 

옵셔널 바인딩은 옵셔널이 값을 가지고 있는지 확인할때 사용합니다 그리고 임시적인 상수나 변수로 값을 사용할 수 있도록 만들 수 있다.



Optional binding can be used with `if` and `while` statements to check for a value inside an optional, and to extract that value into a constant or variable, as part of a single action.

옵셔널 바인딩은 이프문이나 와일문에서 옵셔널 내부 값을 체크하기 위해 사용할 수 있다 그리고 상수나 변수로 값을 적출할 수 있다 단일 엑션의 부분으로



`if` and `while` statements are described in more detail in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

이프나 와일문은 해당 링크에서 더 자세히 설명되어있습니다.



Write an optional binding for an `if` statement as follows:

이프문을 통해 옵셔널 바인딩은 아래와 같이 작성한다.



You can rewrite the `possibleNumber` example from the [Optionals](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID330) section to use optional binding rather than forced unwrapping:

옵셔널 섹션에서 키워드를 다시 작성해서 강제 언래핑을 사용하는 대신 옵셔널 바인딩을 사용할 수 있습니다.



This code can be read as:

“If the optional `Int` returned by `Int(possibleNumber)` contains a value, set a new constant called `actualNumber` to the value contained in the optional.”

이 코드는 이렇게 읽힙니다.

만약 키워드가 값을 갖고, 옵셔널 인티저를 반환한다면, 키워드로 불리는 새로운 상수에 옵셔널 내부 값을 셋해라



If the conversion is successful, the `actualNumber` constant becomes available for use within the first branch of the `if` statement. 

만약 변환이 성공적이다면, 키워드 상수는 이프문의 첫 괄호 내부에서 키워드 이름으로 사용할 수 있습니다.



It has already been initialized with the value contained *within* the optional, and so you don’t use the `!` suffix to access its value. 

이것은 옵셔널 내부에 포함 된 값으로 이미 초기화 되었다, 그리고 값을 접근할 때 ! 접미사를 사용할 필요가 없다.



In this example, `actualNumber` is simply used to print the result of the conversion.

예시에서 키워드는 변환 결과를 갖고 출력하는데 사용된다.



You can use both constants and variables with optional binding. 

당신은 상수나 변수를 옵셔널 바인딩으로 사용할 수 있습니다.



If you wanted to manipulate the value of `actualNumber` within the first branch of the `if` statement, you could write `if var actualNumber` instead, and the value contained within the optional would be made available as a variable rather than a constant.

만약 이프 문 안에서 키워드를 변경하길 원한다면, 당신은 대신 키워드로 작성할 수 있다, 그리고 그 값은 포함된다 상수대신 변수로서 가능하도록 만들어진다.



You can include as many optional bindings and Boolean conditions in a single `if` statement as you need to, separated by commas. 

당신은 분리된 콤마를 사용해서 단일 이프문에서 당신이 원하는 만큼 불린 조건문 그리고 옵셔널 바인딩을 포함할 수 있다.



If any of the values in the optional bindings are `nil` or any Boolean condition evaluates to `false`, the whole `if` statement’s condition is considered to be `false`. 

옵셔널 바인딩 값의 어떤것이든 닐이거나 불린 조건문이 거짓으로 평가받는다면, 이프문 전체 상태가 거짓으로 고려된다.



The following `if` statements are equivalent:

뒤에오는 이프문은 동일합니다.



Constants and variables created with optional binding in an `if` statement are available only within the body of the `if` statement. 

옵셔널 바인딩으로 부터 생성된 상수나 변수는 이프문에서만 사용가능합니다.



In contrast, the constants and variables created with a `guard` statement are available in the lines of code that follow the `guard` statement, as described in [Early Exit](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html#ID525).

대조적으로, 가드문에서  생성된 상수나 변수는 빠른탈출에서 설명된대로, 가드문 뒤에서 사용할 수 있습니다.



suffix: 접미사

manipulate: 조작하다, 처리하다

equivalent: 동등한

In contrast: 대조적으로