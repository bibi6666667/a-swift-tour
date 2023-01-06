# Functions - Function Types (1)

## 함수 타입

모든 함수는 특정한 함수 타입을 갖습니다. 함수 타입은 함수의 파라미터 타입들과 리턴 타입으로 이루어집니다.

예를 들어:

``` swift
func addTwoInts(_ a: Int, _ b: Int) -> Int {
    return a + b
}
func multiplyTwoInts(_ a: Int, _ b: Int) -> Int {
    return a * b
}
```

이 예시는 `addTwoInts` 와 `multiplyTwoInts`라는 두 간단한 수학적 함수들을 정의합니다. 두 함수는 각각 두 개의 Int값을 받고, 적절한 수학적 연산을 실행한 결과로 하나의 Int 값을 반환합니다.

이 두 함수들의 타입은 `(Int, Int) -> Int` 입니다. 이것은 다음과 같이 읽을 수 있습니다 :

"Int 타입의 두 파라미터를 갖고, Int 타입의 값을 반환하는 함수"

여기에 어떤 파라미터와 리턴값도 갖지 않는 또 다른 함수 예시가 있습니다:

``` swift
func printHelloWorld() {
    print("hello, world")
}
```

이 함수의 타입은 `() -> Void` 이며, "파라미터를 갖지 않으면서 Void를 반환하는 함수"라고 읽을 수 있습니다.

### 함수 타입 사용하기

Swift의 다른 모든 타입들과 똑같이 함수 타입을 사용할 수 있습니다. 예를 들어, 상수나 변수를 함수 타입으로 선언하고 그 변수에 적절한 함수를 할당할 수 있습니다:

``` swift
var mathFunction: (Int, Int) -> Int = addTwoInts
```

이것은 다음과 같이 읽을 수 있습니다:

"`mathFunction`이라는 이름의 변수를 정의하고, 그 타입은 '두 개의 Int값을 받고 하나의 Int값을 반환하는 함수'이다. 이 새 변수가 `addTwoInts`라는 함수를 참조하도록 설정한다."

`addTwoInts(_:_:)` 함수는 `mathFunction`변수와 같은 타입을 가지며, 그래서 이 할당은 Swift의 type-checker에 의해 허용됩니다.

이제 `mathFunction`에 할당된 함수를 호출할 수 있습니다:

``` swift
print("Result: \(mathFunction(2, 3))")
// "Result: 5"를 출력합니다.
```

함수가 아닌 타입과 똑같은 방식으로, 같은 변수에 타입이 일치하는 다른 함수를 할당할 수도 있습니다:

``` swift
mathFunction = multiplyTwoInts
print("Result: \(mathFunction(2, 3))")
// "Result: 6"를 출력합니다.
```

다른 모든 타입과 마찬가지로, 상수나 변수에 함수를 할당할 때 Swift가 함수 타입을 추론하도록 둘 수도 있습니다:

``` swift
let anotherMathFunction = addTwoInts
// anotherMathFunction은 (Int, Int) -> Int타입으로 추론됩니다.
```

### 파라미터 타입으로서의 함수 타입

`(Int, Int) -> Int`와 같이, 다른 함수에 대한 파라미터 타입으로서 함수 타입을 사용할 수 있습니다. 이는 함수가 호출될 때 그 함수의 호출자가 제공해야 하는 함수의 구현에 대한 어떤 측면을 남길 수 있도록 합니다.

여기에 위에서 언급한 수학 함수의 결과를 출력하는 예시가 있습니다: 

```swift
func printMathResult(_ mathFunction: (Int, Int) -> Int, _ a: Int, _ b: Int) {
    print("Result: \(mathFunction(a, b))")
}
printMathResult(addTwoInts, 3, 5)
// "Result: 8"를 출력합니다.
```

이 예시는 세 파라미터를 가지는 `printMathResult(_:_:_:)` 함수를 정의합니다. 첫 번째 파라미터는 `mathFunction` 이며, 타입은 `(Int, Int) -> Int` 입니다. 이 타입에 해당하는 어떤 함수이든 이 첫 번째 파라미터의 아규먼트로 넘길 수 있습니다. 두 번째와 세 번째 파라미터는 `a` 와 `b` 이며, 둘의 타입은 모두 Int입니다. 이들은 제공된 수학 함수에 대한 두 입력값으로 사용됩니다.

`printMathResult(_:_:_:)` 가 호출될 때, `addTwoInts(_:_:)` 를 전달하며, 정수 값은 3과 5입니다. 그것은 제공된 함수에 3과 5를 넣어 호출하며, 그 결과로 8을 출력합니다.

`printMathResult(_:_:_:)` 의 역할은 적절한 타입의 수학 함수의 호출 결과를 출력하는 것입니다. 그 함수의 실제로 어떻게 되어 있는지는 중요하지 않습니다 - 중요한 것은 그 함수의 타입이 정확히 일치하는지입니다. 이는 `printMathResult(_:_:_:)` 가 자신의 기능의 일부를 함수의 호출자에게 type-safe한 방법으로 전달할 수 있게 합니다.
