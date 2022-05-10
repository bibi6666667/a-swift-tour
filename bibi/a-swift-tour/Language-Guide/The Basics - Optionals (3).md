# The Basics - Optionals (3)

## Optional Binding

### Optional Binding

You use *optional binding* to find out whether an optional contains a value, and if so, to make that value available as a temporary constant or variable. Optional binding can be used with `if` and `while` statements to check for a value inside an optional, and to extract that value into a constant or variable, as part of a single action. `if` and `while` statements are described in more detail in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

Write an optional binding for an `if` statement as follows:

``` swift
if let constantName = someOptional {
    statements
}
```

You can rewrite the `possibleNumber` example from the [Optionals](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID330) section to use optional binding rather than forced unwrapping:

``` swift
if let actualNumber = Int(possibleNumber) {
    print("The string \"\(possibleNumber)\" has an integer value of \(actualNumber)")
} else {
    print("The string \"\(possibleNumber)\" couldn't be converted to an integer")
}
// Prints "The string "123" has an integer value of 123"
```

This code can be read as:

“If the optional `Int` returned by `Int(possibleNumber)` contains a value, set a new constant called `actualNumber` to the value contained in the optional.”

If the conversion is successful, the `actualNumber` constant becomes available for use within the first branch of the `if` statement. It has already been initialized with the value contained *within* the optional, and so you don’t use the `!` suffix to access its value. In this example, `actualNumber` is simply used to print the result of the conversion.

You can use both constants and variables with optional binding. If you wanted to manipulate the value of `actualNumber` within the first branch of the `if` statement, you could write `if var actualNumber` instead, and the value contained within the optional would be made available as a variable rather than a constant.

You can include as many optional bindings and Boolean conditions in a single `if` statement as you need to, separated by commas. If any of the values in the optional bindings are `nil` or any Boolean condition evaluates to `false`, the whole `if` statement’s condition is considered to be `false`. The following `if` statements are equivalent:

``` swift
if let firstNumber = Int("4"), let secondNumber = Int("42"), firstNumber < secondNumber && secondNumber < 100 {
    print("\(firstNumber) < \(secondNumber) < 100")
}
// "4 < 42 < 100" 를 출력합니다.

if let firstNumber = Int("4") {
    if let secondNumber = Int("42") {
        if firstNumber < secondNumber && secondNumber < 100 {
            print("\(firstNumber) < \(secondNumber) < 100")
        }
    }
}
// "4 < 42 < 100" 를 출력합니다.
```

>  NOTE
>
> Constants and variables created with optional binding in an `if` statement are available only within the body of the `if` statement. In contrast, the constants and variables created with a `guard` statement are available in the lines of code that follow the `guard` statement, as described in [Early Exit](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html#ID525).





---

## Optional Binding

옵셔널 바인딩

옵셔널이 값을 가지고 있는지 확인하고, 만약 가지고 있다면 그 값을 일시적인 상수나 변수로 사용 가능하도록 만들기 위해 *옵셔널 바인딩*을 사용합니다. 옵셔널 바인딩은 한 동작으로 옵셔널 안의 값을 확인하기 위해, 그리고 그 값을 상수나 변수로 추출하기 위해 `if`와 `while`문과 함께 사용될 수 있습니다. `if` 와 `while` 문은 [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)에 더 자세히 설명되어 있습니다.

아래와 같이 if문으로 옵셔널 바인딩을 작성하십시오:

``` swift
if let 상수이름 = 어떤옵셔널 {
    구문들
}
```

Optionals 부분으로부터의 예시인 `possibleNumber` 를 강제 언래핑보다는 옵셔널 바인딩을 사용하도록 다시 작성할 수 있습니다:

``` swift
if let actualNumber = Int(possibleNumber) {
    print("The string \"\(possibleNumber)\" has an integer value of \(actualNumber)")
} else {
    print("The string \"\(possibleNumber)\" couldn't be converted to an integer")
}
// "The string "123" has an integer value of 123" 출력
```

이 코드는 다음과 같이 읽을 수 있습니다:

"만약 `Int(possibleNumber)`로부터 반환된 옵셔널 Int가 값을 가지고 있다면, `actualNumber`라는 이름의 새 상수를 옵셔널에 담긴 값으로 설정해라."

만약 변환이 성공적이라면, `actualNumber` 상수는 if문의 첫 번째 분기 내에서 사용할 수 있게 됩니다. 그것은 옵셔널 안에 포함된 값으로 이미 초기화되어 있으며, 따라서 그 값에 접근하기 위해  `!`접미사를 사용할 필요가 없습니다. 이 예시에서, `actualNumber`는 변환의 결과를 출력하기 위해 간단히 사용되었습니다.

옵셔널 바인딩에서는 상수와 변수를 모두 사용할 수 있습니다. 만약 `actualNumber`의 값을 if문 첫 번째 범위 내에서 처리하고 싶었다면, `if var actualNumber`라고 대신 작성할 수 있으며, 옵셔널 내의 값은 상수가 아닌 변수로 사용 가능합니다.

당신은 쉼표(`,`)로 구분하여 하나의 if문 안에 필요한 만큼의 옵셔널 바인딩과 불리언 조건식을 포함할 수 있습니다. 만약 옵셔널 바인딩 내의 값 중 하나라도 nil이 있거나, 불리언 조건식 중 하나라도 false가 되면, 전체 if문의 조건식은 false로 간주됩니다. 아래 if문과 같습니다:

``` swift
if let firstNumber = Int("4"), let secondNumber = Int("42"), firstNumber < secondNumber && secondNumber < 100 {
    print("\(firstNumber) < \(secondNumber) < 100")
}
// "4 < 42 < 100" 를 출력합니다.

if let firstNumber = Int("4") {
    if let secondNumber = Int("42") {
        if firstNumber < secondNumber && secondNumber < 100 {
            print("\(firstNumber) < \(secondNumber) < 100")
        }
    }
}
// "4 < 42 < 100" 를 출력합니다.
```

> 노트
>
> if문 내에서 옵셔널 바인딩으로 만들어진 상수와 변수는 if문 내에서만 사용이 가능합니다. 대조적으로, [Early Exit](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html#ID525)에 설명된 것처럼, guard문으로 만들어진 상수와 변수는 guard문 이후의 코드 줄에서도 사용이 가능합니다. 



---

## 단어 정리

- manipulate 처리하다. 조종하다.
- equivalent (형) 동등한. (명) 등가물.
- In contrast 대조적으로.