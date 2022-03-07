# Booleans

Swift has a basic *Boolean* type, called `Bool`.

불로 불리는 기본 불의 타입이 있다.



Boolean values are referred to as *logical*, because they can only ever be true or false. 

불의 값은 논리적으로 추론된다. 왜냐하면 그들은 오직 트루 똔느 폴스로만 정의된다.



Swift provides two Boolean constant values, `true` and `false`:

스위프트는 두가지 불의 상수값을 제공한다 참 그리고 거짓.



The types of `orangesAreOrange` and `turnipsAreDelicious` have been inferred as `Bool`from the fact that they were initialized with Boolean literal values. 

키워드 그리고 키워드의 타입은 불의 상수값으로 초기화 됐기 때문에 불로 추론되어진다.



As with `Int` and `Double`above, you don’t need to declare constants or variables as `Bool` if you set them to `true` or `false` as soon as you create them. 

인트와 더블과 마찬가지로 당신은 생성할 때 참이나 거짓을 셋할 필요는 없습니다.



Type inference helps make Swift code more concise and readable when it initializes constants or variables with other values whose type is already known.

타입 추론은 상수 또는 변수의 타입이 이미 알고 있을때 다른 값으로 초기화할 때 스위프트 코드를 간결하고 읽기 쉽게 만듭니다.



Boolean values are particularly useful when you work with conditional statements such as the `if`statement:

불린 값은 이프문과 같은 조건문을 사용할 때 특별하게 사용됩니다. 



Conditional statements such as the `if` statement are covered in more detail in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

이프문과 같은 조건문은 컨트롤 플로우에서 자세하게 다루도록 하겠습니다.



Swift’s type safety prevents non-Boolean values from being substituted for `Bool`. 

스위프트 타입 안전은 불 값을 불값이 아닌 값이 대신하는 걸 예방합니다.



The following example reports a compile-time error:

따라오는 예시를 보면 컴파일 타임에 에러를 신고합니다.



However, the alternative example below is valid:

그러나 두번째 예시는 유효합니다.



The result of the `i == 1` comparison is of type `Bool`, and so this second example passes the type-check. 

해당 비교의 타입의 결과값은 불입니다. 그리고 두번 째 예시는 타입체크 를 패스합니다.



Comparisons like `i == 1` are discussed in [Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html).

기본 오퍼레이터에서 토론되었습니다.



As with other examples of type safety in Swift, this approach avoids accidental errors and ensures that the intention of a particular section of code is always clear.

다른 예시의 스위프트의 타입 안전처럼 갑작스러운 에러를 피하며 코드의 의도가 명확하도록 보장합니다.



concise: 간결한

substituted:  대리

intention: 의도