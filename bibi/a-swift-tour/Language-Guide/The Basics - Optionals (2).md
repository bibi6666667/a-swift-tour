# The Basics - Optionals (2)



### nil

You set an optional variable to a valueless state by assigning it the special value `nil`:

``` swift
var serverResponseCode: Int? = 404
// serverResponseCode contains an actual Int value of 404
serverResponseCode = nil
// serverResponseCode now contains no value
```

>  NOTE
>
> You can’t use `nil` with non-optional constants and variables. If a constant or variable in your code needs to work with the absence of a value under certain conditions, always declare it as an optional value of the appropriate type.

If you define an optional variable without providing a default value, the variable is automatically set to `nil` for you:

``` swift
var surveyAnswer: String?
// surveyAnswer is automatically set to nil
```

> NOTE
>
> Swift’s `nil` isn’t the same as `nil` in Objective-C. In Objective-C, `nil` is a pointer to a nonexistent object. In Swift, `nil` isn’t a pointer—it’s the absence of a value of a certain type. Optionals of *any* type can be set to `nil`, not just object types.

### If Statements and Forced Unwrapping

You can use an `if` statement to find out whether an optional contains a value by comparing the optional against `nil`. You perform this comparison with the “equal to” operator (`==`) or the “not equal to” operator (`!=`).

If an optional has a value, it’s considered to be “not equal to” `nil`:

``` swift
if convertedNumber != nil {
    print("convertedNumber contains some integer value.")
}
// Prints "convertedNumber contains some integer value."
```

Once you’re sure that the optional *does* contain a value, you can access its underlying value by adding an exclamation point (`!`) to the end of the optional’s name. The exclamation point effectively says, “I know that this optional definitely has a value; please use it.” This is known as *forced unwrapping* of the optional’s value:

``` swift
if convertedNumber != nil {
    print("convertedNumber has an integer value of \(convertedNumber!).")
}
// Prints "convertedNumber has an integer value of 123."
```

For more about the `if` statement, see [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

>  NOTE
>
> Trying to use `!` to access a nonexistent optional value triggers a runtime error. Always make sure that an optional contains a non-`nil` value before using `!` to force-unwrap its value.





---



### nil

특별한 값인 `nil`을 할당함으로서 옵셔널 변수를 값이 없는 상태로 설정할 수 있습니다 : 

``` swift
var serverResponseCode: Int? = 404
// serverResponseCode는 404라는 실제 Int값을 담고 있습니다
serverResponseCode = nil
// serverResponseCode는 이제 어떤 값도 담고 있지 않습니다
```

> 노트
>
> 옵셔널이 아닌 상수와 변수에는 nil 을 사용할 수 없습니다. 만약 당신의 코드의 상수나 변수가 특정 조건에서 값의 없음을 다뤄야 한다면, 항상 적절한 타입의 옵셔널 값으로 선언하십시오.

만약 기본값을 제공하지 않고 옵셔널 변수를 정의한다면, 그 변수는 당신을 위해 자동으로 nil 로 설정될 것입니다:

``` swift
var surveyAnswer: String?
// surveyAnswer는 자동으로 nil로 설정됩니다
```

> 노트
>
> 스위프트의 nil 은 Objective-C의 nil과 같지 않습니다. Objective-C 에서는, nil 은 존재하지 않는 객체에 대한 포인터입니다. 스위프트에서는, nil은 포인터가 아닙니다 - 그것은 특정 타입의 값의 없음입니다. 객체 타입 뿐 아니라, 어떤 타입의 옵셔널이든 nil로 설정될 수 있습니다.

### If Statements and Forced Unwrapping

if 구문과 강제 언래핑

옵셔널이 값을 담고 있는지 알기 위해, 옵셔널과 nil 을 비교함으로서 if 구문을 사용할 수 있습니다. '같음' 연산자(`==`) 또는 '같지 않음' 연산자(`!=`)로 이 비교를 수행합니다.

만약 옵셔널이 값을 가지면, nil 과 "같지 않다"고 간주됩니다 :

``` swift
if convertedNumber != nil {
    print("convertedNumber contains some integer value.")
}
// "convertedNumber contains some integer value."를 출력합니다
```

당신이 옵셔널이 정말로 값을 담고 있다고 확신할 때, 옵셔널의 이름 끝에 느낌표(`!`)를 붙임으로서 그 밑에 있는 값에 접근할 수 있습니다. 느낌표는 "나는 이 옵셔널이 분명히 값을 가지고 있음을 알아. 이 값을 사용해"라고 효과적으로 말합니다. 이것은 옵셔널 값의 *강제 언래핑*이라고 알려져 있습니다 :

``` swift
if convertedNumber != nil {
    print("convertedNumber has an integer value of \(convertedNumber!).")
}
// "convertedNumber has an integer value of 123."을 출력합니다.
```

if 문에 대한 더 많은 정보는 [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)를 확인하십시오.

> 노트
>
> 존재하지 않는 옵셔널 값에 접근하기 위해 `!`를 사용하는 것은 런타임 에러를 유발합니다. 옵셔널 값에 강제 언래핑을 위해 `!`을 사용하기 전에, 옵셔널이 nil이 아닌 값을 담고 있음을 항상 확인하십시오.

---

## 단어 정리

- once ...할 때. 일단. 한 번.
- exclamation point 느낌표
- underlying 밑에 있는. 뒤에 숨은.
- effectively 효과적으로. 실제로.
- definitely 분명히