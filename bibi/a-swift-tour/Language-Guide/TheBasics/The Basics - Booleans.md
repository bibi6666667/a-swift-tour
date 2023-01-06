# The Basics - Booleans

> Swift has a basic *Boolean* type, called `Bool`. Boolean values are referred to as *logical*, because they can only ever be true or false. Swift provides two Boolean constant values, `true` and `false`:
>
> ``` swift
> let orangesAreOrange = true
> let turnipsAreDelicious = false
> ```
>
> The types of `orangesAreOrange` and `turnipsAreDelicious` have been inferred as `Bool` from the fact that they were initialized with Boolean literal values. As with `Int` and `Double` above, you don’t need to declare constants or variables as `Bool` if you set them to `true` or `false` as soon as you create them. Type inference helps make Swift code more concise and readable when it initializes constants or variables with other values whose type is already known.
>
> Boolean values are particularly useful when you work with conditional statements such as the `if` statement:
>
> ``` swift
> if turnipsAreDelicious {
>     print("Mmm, tasty turnips!")
> } else {
>     print("Eww, turnips are horrible.")
> }
> // Prints "Eww, turnips are horrible."
> 
> ```
>
> Conditional statements such as the `if` statement are covered in more detail in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).
>
> Swift’s type safety prevents non-Boolean values from being substituted for `Bool`. The following example reports a compile-time error:
>
> ``` swift
> let i = 1
> if i {
>     // this example will not compile, and will report an error
> }
> 
> ```
>
> However, the alternative example below is valid:
>
> ``` swift
> let i = 1
> if i == 1 {
>     // this example will compile successfully
> }
> ```
>
> The result of the `i == 1` comparison is of type `Bool`, and so this second example passes the type-check. Comparisons like `i == 1` are discussed in [Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html).
>
> As with other examples of type safety in Swift, this approach avoids accidental errors and ensures that the intention of a particular section of code is always clear.

---

## Booleans

불리언

스위프트는 `Bool` 이라고 하는 기본 불리언 타입을 가지고 있습니다. 불리언 값들은 논리적인 것을 나타냅니다. 왜냐하면 불리언은 참 또는 거짓만 될 수 있기 때문입니다. 스위프트는 두 불리언 상수 값인 `true` 와 `false` 를 제공합니다:

``` swift
let orangesAreOrange = true
let turnipsAreDelicious = false
```

`orangesAreOrange`와 `turnipsAreDelicious`의 타입은 불리언 리터럴 값으로 초기화되었다는 점에서 Bool로 추론됩니다. `Int`와 `Double`처럼, 상수나 변수를 만들 때 true나 false로 초기화했다면 Bool로 선언할 필요는 없습니다. 타입 추론은 상수나 변수를 이미 타입이 알려진 다른 값으로 초기화할 때 스위프트 코드를 더 간결하고 읽기 쉽게 만들어 줍니다 .

불리언 값은 if문과 같은 조건문을 다룰 때 특히 유용합니다 :

``` swift
if turnipsAreDelicious {
    print("Mmm, tasty turnips!")
} else {
    print("Eww, turnips are horrible.")
}
// "Eww, turnips are horrible."를 출력합니다.
```

if문과 같은 조건문은 [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)에 더 자세히 설명되어 있습니다.

스위프트의 타입 안전은 불리언이 아닌 값이 Bool 대신 사용되는 것을 막습니다. 이어지는 예시는 컴파일 타임 에러를 보고합니다 :

``` swift
let i = 1
if i {
    // 이 예시는 컴파일되지 않고, 에러를 보고할 것입니다
}
```

하지만, 아래의 대체되는 예시는 유효합니다 :

``` swift
let i = 1
if i == 1 {
    // 이 예시는 성공적으로 컴파일될 것입니다
}
```

`i == 1` 비교의 결과의 타입은 Bool이며, 따라서 이 두 번째 예시는 타입-확인을 통과합니다. `i == 1`같은 비교는 [Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html)에 기술되어 있습니다.

스위프트의 다른 타입 안전 예시들처럼, 이 접근은 우연한 에러를 피하고 코드의 어떤 부분의 의도가 항상 명확하도록 보장해 줍니다.



---

## 단어 정리

- boolean 불. 불의.
- refer to ...를 나타내다
- concise 간결한
- readable 읽기 쉬운
- substitute 대신하다
- comparision 비교
- intention 의도
- as soon as ... 하자마자.

