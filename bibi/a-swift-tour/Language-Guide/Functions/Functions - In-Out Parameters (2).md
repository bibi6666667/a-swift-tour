# Functions - In-Out Parameters (2)

> https://docs.swift.org/swift-book/LanguageGuide/Functions.html#:~:text=the%20variadic%20parameter.-,In%2DOut%20Parameters,-Function%20parameters%20are

여기 `swapTwoInts(_:_:)`라는 이름과, a와 b라는 두 in-out 정수 파라미터를 갖는 함수 예시가 있습니다:

``` swift
func swapTwoInts(_ a: inout Int, _ b: inout Int) {
    let temporaryA = a
    a = b
    b = temporaryA
}
```

`swapTwoInts(_:_:)` 함수는 단순히 b를 a로, a를 b로 맞바꾸는 함수입니다. 이 함수는 a의 값을 `temporaryA`라는 임시 상수애 저장한 다음, b의 값을 a에 할당하고, `temporaryA`를 b에 할당함으로써 값을 맞바꿉니다.

`swapTwoInts(_:_:)`함수는 값을 맞바꿀 두 Int타입 변수가 있어야 호출할 수 있습니다. `someInt`와 `anotherInt`가 전달될 때, 두 값의 이름 앞에 앰퍼샌드(`&`)가 붙어 있음에 주목하십시오:

``` swift
var someInt = 3
var anotherInt = 107
swapTwoInts(&someInt, &anotherInt)
print("someInt is now \(someInt), and anotherInt is now \(anotherInt)")
// "someInt is now 107, and anotherInt is now 3"를 출력합니다.
```

위의 예시 는`someInt`와 `anotherInt` 값이 원래 함수 밖에서 선언되었음에도 원래 값이  `swapTwoInts(_:_:)`에 의해 바뀌었음을 보여줍니다.

> 노트
>
> in-out 파라미터는 함수로부터 값을 반환하는 것과는 다릅니다. 위의 `swapTwoInts` 예시는 리턴 타입을 정의하거나 값을 리턴하지 않지만, 그럼에도 `someInt`와 `anotherInt`의 값을 변경합니다. in-out 파라미터는 함수가 자신의 body의 스코프 바깥에 영향을 끼칠 수 있는 대안적인 방법입니다. 