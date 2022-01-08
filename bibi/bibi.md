# The Swift Programming Language - Swift 5.5

> https://docs.swift.org/swift-book/#

**🐯 bibi가 해석한 문서입니다.**

---

## 목차

- [WELCOME TO SWIFT](#welcome-to-swift)
  * [About Swift](#about-swift)
  * [Version Compatibility](#version-compatibility)
  * [A Swift Tour](#a-swift-tour)
    + [Hello, world](#hello--world)
    + [Simple Values](#simple-values)
    + [Control Flow](#control-flow)
    + [Functions and Closures](#functions-and-closures)
    + [Objects and Classes](#objects-and-classes)
    + [Enumerations and Structures](#enumerations-and-structures)
    + [Protocols and Extensions](#protocols-and-extensions)
    + [Error Handling](#error-handling)
    + [Generics](#generics)
- [LANGUAGE GUIDE](#language-guide)
  * [The Basics](#the-basics)
    + [Constants and Variables](#constants-and-variables)
      - [Declaring Constants and Variables](#declaring-constants-and-variables)
      - [Type Annotations](#type-annotations)
      - [Naming Constants and Variables](#naming-constants-and-variables)
      - [Printing Constants and Variables](#printing-constants-and-variables)
    + [Comments](#comments)
    + [Semicolons](#semicolons)
    + [Integers](#integers)
      - [Integer Bounds](#integer-bounds)
      - [Int](#int)
      - [UInt](#uint)
    + [Floating-Point Numbers](#floating-point-numbers)
    + [Type Safety and Type Inference](#type-safety-and-type-inference)

---

# WELCOME TO SWIFT

## About Swift

> https://docs.swift.org/swift-book/#

Swift에 대하여.

Swift는 소프트웨어를 작성하는 환상적인 방법입니다. 핸드폰, 데스크탑, 서버 등 어떤 것을 위한 소프트웨어든지 코드를 실행하는 모든 것에 대해서 말입니다. Swift는 안전하고, 빠르고, 상호작용적인 프로그래밍 언어이며 현대 프로그래밍 언어 사고방식의 장점, Apple 개발 문화로부터의 지혜, 그리고 오픈소스 커뮤니티로부터의 다양한 기여의 종합체입니다. 서로 간에 어떤 타협도 없이, 컴파일러는 성능을 위해 최적화 되어 있으며 언어는 개발을 위해 최적화되어 있습니다.

Swift는 초보 프로그래머들에게 친숙합니다. Swift는 산업을 위한 품질의 프로그래밍 언어만큼 표현적이며, 스크립트 언어만큼 즐겁습니다. Playground에서 Swift 코드를 작성하는 것은 당신이 코드로 실험하는 것과 그 결과를 보는 것을 애플리케이션 빌드와 실행을 기다릴 필요 없이 즉각적으로 해 줍니다.

Swift는 일반적인 프로그래밍 에러들의 방대한 클래스들을 현대 프로그래밍 패턴을 적용함으로써 정의해 두었습니다 :

- 변수들은 사용되기 전에 항상 초기화됩니다.
- 배열 인덱스들은 out-of-bounds error에 대해 확인됩니다.
- 정수형은 overflow에 대해 확인됩니다.
- 옵셔널은 nil 값이 분명하게 다루어지도록 확실히 해 줍니다.
- 메모리는 자동으로 관리됩니다.
- 오류 처리는 갑작스러운 실패로부터 통제된 회복을 가능하게 합니다.

Swift 코드는 현대 하드웨어로부터 최고를 끌어내기 위해 컴파일 및 최적화 되었습니다. 문법과 표준 라이브러리는 코드를 작성하기 위한 분명한 방법이 최고로 기능하도록 하는 안내 원칙에 기반하여 디자인되었습니다. 안전성과 속도의 결합은 "Hello, world!" 부터 전체 운영체제까지 Swift가 최고의 선택이도록 합니다.

Swift는 강력한 타입 추론과 패턴 매칭, 현대적이고 가벼운 문법을 결합해 복잡한 아이디어가 명확하고 간결한 방식으로 표현되도록 합니다. 그 결과로, 코드는 작성하기 쉬울 뿐 아니라 읽기도 유지보수하기에도 더 쉽습니다.

Swift는 수 년에 걸쳐 만들어져 왔으며, 새로운 특징 및 능력과 함께 계속해서 진화하고 있습니다. Swift에 대한 우리의 목표는 야망적입니다. 우리는 당신이 Swift로 무엇을 창조해낼지 매우 기대됩니다.

## Version Compatibility

> https://docs.swift.org/swift-book/GuidedTour/Compatibility.html

버전 호환성.

이 책은 Xcode 13에 포함된 Swift의 기본 버전인 Swift 5.5에 대해 서술하고 있습니다. 당신은 Swift 5.5, Swift 4.2, Swift 4로 쓰여진 타겟을 빌드하기 위해 Xcode 13을 사용할 수 있습니다.

Swift 4와 Swift 4.2 코드를 빌드하기 위해 Xcode 13을 사용할 때, Swift 5.5의 대부분의 기능성이 사용 가능합니다. 그렇긴 하지만, 아래의 변화들은 Swift 5.5 이상 버전을 사용하는 코드에서만 사용 가능합니다 :

- 불분명 타입을 반환하는 함수들은 실행 시간에 Swift 5.1을 요구합니다.
- `try?` 표현은 이미 옵셔널을 반환하는 표현들에 대한 추가적인 수준의 선택성을 소개하지 않습니다.
- 큰 정수 리터럴 초기화 표현은 올바른 정수 타입이 되도록 추론됩니다. 예를 들어, `UInt64(0xffff_ffff_ffff_ffff)` 는 오버플로되기보다는 올바른 정수 타입으로 평가합니다.

동시 실행은 Swift 5.5 이상과, 상응하는 동시 실행 타입들을 제공하는  Swift 표준 라이브러리를 요구합니다. Apple 플랫폼들에서, 배포 타겟을 최소한 iOS 15, macOS 12, tvOS 15, watchOS 8.0으로 설정하십시오.

Swift 5.5로 작성된 타겟은 Swift 4.2 또는 Swift 4로 작성된 타겟에 의존할 수 있으며, 그 반대도 성립합니다. 이는 만약 당신이 여러 개의 프레임워크들로 나뉘어진 거대한 프로젝트를 가지고 있다면, 당신은 Swift 4에서 Swift 5.5로 한 번에 한 프레임워크를 옮길 수 있음을 의미합니다.

## A Swift Tour

> https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html

### Hello, world

전통적으로 새로운 언어의 첫 프로그램은 "Hello, world!"를 화면에 출력하는 것입니다. Swift에서, 이는 아래의 한 줄로 가능합니다 : 

```swift
print("Hello, world!")
// Prints "Hello, world!"
```

만약 당신이 C나 Objective-C로 코드를 작성한 적이 있다면, 이 문법은 당신에게 친숙해 보일 것입니다 - Swift에서, 이 코드 한 줄은 하나의 완전한 프로그램입니다. 당신은 입력/출력이나 문자열 다루기와 같은 기능을 위해 별도의 라이브러리를 불러올 필요가 없습니다. 전역 스코프로 작성된 코드는 그 프로그램의 엔트리 포인트로 사용되기 때문에, `main()` 함수가 필요없습니다. 또한 모든 구문의 끝에 세미콜론을 작성할 필요도 없습니다.

이 tour는 다양한 프로그래밍 과제를 성취하는 법을 보여줌으로써 Swift로 코드를 작성하기 시작하기 위한 충분한 정보를 줄 것입니다. 어떤 것을 이해하지 못하더라도 걱정하지 마세요 - 이 tour에 소개된 모든 것은 이 책의 나머지에 자세히 설명되어 있습니다.

> 메모
>
> 최고의 경험을 위해, 이 챕터를 Xcode의 playground로 여십시오. Playgrounds는 코드 리스트들을 편집하고 그 결과를 즉시 볼 수 있도록 합니다.
>
> [Playground 다운로드](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.playground.zip)

### Simple Values

단순한 값.

상수를 만들기 위해 `let`을, 변수를 만들기 위해 `var`를 사용하십시오. 상수의 값은 컴파일 시점에 알려질 필요는 없지만, 반드시 단 한 번만 할당되어야 합니다. 이것은 당신이 한 번 결정하지만 여러 곳에서 사용할 값에 이름을 붙이기 위해 상수들을 사용할 수 있음을 의미합니다.

``` swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```

상수 또는 변수는 당신이 그것에 할당하기를 원하는 값과 반드시 같은 타입을 가져야 합니다. 하지만, 항상 타입을 명시적으로 작성해야 하는 것은 아닙니다. 상수나 변수를 만들 때 값을 제공하는 것은 컴파일러가 그것의 타입을 추론하도록 해 줍니다. 위의 예시에서, 컴파일러는 `myVariable`가 정수형임을 추론하는데, 이는 그것의 초기값이 정수이기 때문입니다.

만약 초기값이 충분한 정보를 제공하지 않는다면 (또는 그것이 초기값이 아니라면), 콜론으로 구분된 타입을 변수 뒤에 적어 구체화하십시오.

```swift
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
```

> 실험
>
> 명시적 타입이 Float이고 값이 4인 상수를 만들어 보십시오.
>
> `let explicitFloat: Float = 4`

값은 절대로 암묵적으로 다른 타입으로 변환되지 않습니다. 만약 값을 다른 타입으로 변환해야 한다면, 명시적으로 원하는 타입의 인스턴스를 만드십시오.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

> 실험
>
> 마지막 줄에서 String으로의 변환을 지워 보십시오. 어떤 에러를 마주하게 됩니까?
>
> `error: binary operator '+' cannot be applied to operands of type 'String' and 'Int'`

문자열에 값을 포함하기 위한 더욱 간단한 방법이 있습니다 : 소괄호 안에 값을 적고, 소괄호 앞에 백슬래시(`\`)를 적으십시오. 예를 들어 :

```swift
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```

> 실험
>
> 문자열 안에서 부동소수점 계산을 포함하기 위해, 그리고 인사에 누군가의 이름을 포함하기 위해 `\()`를 사용해 보십시오.
>
> ``` swift
> let version = 10.0
> let tinyUpdate = 0.1
> let name = "bibi"
> let greeting = "Hello \(bibi), this program is \(version + tinyUpdate) version."
> ```

여러 줄을 차지하는 문자열에 대해서는 세 큰따옴표(`"""`)를 사용하십시오. 닫는 따옴표의 들여쓰기와 맞을 때까지, 각 인용된 줄 앞의 들여쓰기는 삭제됩니다. 예를 들어 :

``` swift
let quotation = """
I said "I have \(apples) apples."
And then I said "I have \(apples + oranges) pieces of fruit."
"""
```

대괄호(`[]`)를 이용해 배열과 딕셔너리를 만들고, 인덱스나 키를 대괄호 안에 적음으로써 그것들의 원소에 접근하십시오. 마지막 원소 뒤에 콤마는 허용됩니다.

``` swift
var shoppingList = ["catfish", "water", "tulips"]
shoppingList[1] = "bottle of water"

var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```

배열은 당신이 원소를 추가할 때 마다 자동으로 늘어납니다.

``` swift
shoppingList.append("blue paint")
print(shoppingList)
```

빈 배열이나 딕셔너리를 만들기 위해서는, 초기화 구문을 사용하십시오.

``` swift
let emptyArray: [String] = []
let emptyDictionary: [String: Float] = [:]
```

타입 정보가 추론될 수 있다면, 빈 배열은 `[]`로, 빈 딕셔너리는 `[:]`로 작성할 수 있습니다 - 예를 들어, 변수를 위한 새 값을 설정할 때나 함수에 전달인자를 전달할 때.

``` swift
shoppingList = []
occupations = [:]
```

### Control Flow

제어 흐름. 

조건문을 만들기 위해 `if` 와 `switch`를, 그리고 반복문을 만들기 위해 `for-in`, `while`, `repeat-while` 을 사용하십시오. 조건문이나 반복문 주위의 소괄호는 선택 사항입니다. 몸통 주변의 중괄호는 필수 사항입니다.

```swift
let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individualScores {
    if score > 50 {
        teamScore += 3
    } else {
        teamScore += 1
    }
}
print(teamScore)
// Prints "11"
```

`if` 구문에서, 조건문은 반드시 Boolean 표현식이어야 합니다 - 이는 `if score { ... }` 와 같은 코드는 0에 대한 암시적인 비교가 아니라 에러임을 의미합니다.

없을 수 있는 값을 다루기 위해 `if` 와  `let` 을 함께 사용할 수도 있습니다. 대표적으로 옵셔널과 같은 값이 있습니다. 옵셔널 값은 값을 담고 있거나, 값이 없음을 나타내기 위해 `nil`을 담고 있습니다. 값을 옵셔널로 표시하기 위해 값의 타입 뒤에 물음표(`?`) 를 붙이십시오.

```swift
var optionalString: String? = "Hello"
print(optionalString == nil)
// Prints "false"

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
```

> 실험
>
> `optionalName` 을  `nil` 로 바꾸십시오. 어떤 인사를 받게 됩니까? (없음)
>
> `optionalName` 이 `nil` 일 때 받기 위한 다른 인사를 지정하는 `else` 절을 추가하십시오.

만약 옵셔널 값이 nil 이라면, 조건문은 false가 되고 중괄호 속의 코드는 건너뛰게 됩니다. 그렇지 않으면, 옵셔널 값은 벗겨지고 let 뒤의 상수에 할당되어 벗겨진 값을 코드 블록 내에서 쓸 수 있게 됩니다.

옵셔널 값을 다루는 다른 방법은 `??` 연산자를 사용해 기본값을 제공하는 것입니다. 만약 옵셔널의 값이 없다면, 기본값이 대신 사용됩니다.

``` swift
let nickname: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickname ?? fullName)"
```

switch문은 모든 종류의 데이터와 넓고 다양한 범위의 비교 연산을 지원합니다 - switch문은 정수형과 동등성을 위한 테스트에 한정되지 않습니다.

``` swift
let vegetable = "red pepper"
switch vegetable {
case "celery":
    print("Add some raisins and make ants on a log.")
case "cucumber", "watercress":
    print("That would make a good tea sandwich.")
case let x where x.hasSuffix("pepper"):
    print("Is it a spicy \(x)?")
default:
    print("Everything tastes good in soup.")
}
// Prints "Is it a spicy red pepper?"
```

> 실험
>
> default 케이스를 삭제해 보십시오. 어떤 에러를 보게 됩니까?
>
> `Switch must be exhaustive` : switch문은 포괄적이어야 합니다.

패턴에 맞는 값을 상수에 할당하기 위한 패턴에서 let이 어떻게 사용될 수 있는지에 대해 주목하십시오. (`case let x where x.hasSuffix("pepper"):`)

매치되는 switch의 case의 코드를 실행한 뒤에, 프로그램은 switch문을 빠져나옵니다. 실행은 다음 case로 계속되지 않으므로, switch의 case의 코드마다 매번 명시적으로 나갈(break를 쓸) 필요가 없습니다.

딕셔너리의 항목들을 반복하기 위해 각 키-값 쌍에 사용하기 위한 한 쌍의 이름들을 제공함으로써 for-in을 사용할 수 있습니다. 딕셔너리는 순서가 없는 컬렉션이므로, 그 키와 값들은 임의의 순서로 반복됩니다.

```swift
let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
]
var largest = 0
for (_, numbers) in interestingNumbers {
    for number in numbers {
        if number > largest {
            largest = number
        }
    }
}
print(largest)
// Prints "25"
```

> 실험
>
> _ 를 변수 이름으로 대체하고, 어떤 종류의 숫자가 가장 큰 숫자인지 계속 추적해 보세요.

조건이 변화할 때 까지 코드 블럭을 반복하기 위해 while을 사용해 보세요. 반복문의 조건은 맨 끝에 있을 수도 있으며, 그 반복문이 최소 한 번은 실행되게 합니다.

```swift
var n = 2
while n < 100 {
    n *= 2
}
print(n)
// Prints "128"

var m = 2
repeat {
    m *= 2
} while m < 100
print(m)
// Prints "128"
```

인덱스 범위를 만들기 위해 `..<`를 사용함으로써 반복문의 인덱스를 유지할 수 있습니다.

```swift
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
// Prints "6"
```

상위 값을 포함하지 않는 범위를 만들기 위해 `..<`를, 양쪽 값을 포함하는 범위를 만들기 위해 `...`를 사용하십시오.

### Functions and Closures

함수와 클로저.

함수를 선언하기 위해 `func`을 사용하십시오. 함수의 이름과 소괄호 속의 전달인자들을 함께 적음으로써 함수를 호출하십시오. 매개변수 이름 및 타입을 함수의 반환 타입으로부터 분리하기 위해 `->`를 사용하십시오.

```swift
func greet(person: String, day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet(person: "Bob", day: "Tuesday")

```

> 실험
>
> `day` 매개변수를 삭제하십시오. 인사 속에 오늘의 점심 특선을 포함하기 위한 매개변수를 추가하십시오.

기본적으로, 함수는 매개변수 이름을 전달인자를 위한 레이블로 사용합니다. 직접 지은 전달인자 레이블은 매개변수 이름 앞에 적고, 전달인자 레이블을 사용하지 않으려면 `_`를 매개변수 이름 앞에 적으십시오.

``` swift
func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

복합적인 값을 만들기 위해 튜플을 사용하십시오 - 예를 들어, 함수로부터 다수의 값들을 반환하기 위해서입니다. 튜플의 요소들은 이름 또는 숫자를 통해 참조될 수 있습니다.

```swift
func calculateStatistics(scores: [Int]) -> (min: Int, max: Int, sum: Int) {
    var min = scores[0]
    var max = scores[0]
    var sum = 0

    for score in scores {
        if score > max {
            max = score
        } else if score < min {
            min = score
        }
        sum += score
    }

    return (min, max, sum)
}
let statistics = calculateStatistics(scores: [5, 3, 100, 3, 9])
print(statistics.sum)
// Prints "120"
print(statistics.2)
// Prints "120"
```

함수는 중첩될 수 있습니다. 중첩된 함수는 바깥쪽 함수에 선언된 변수에 접근할 수 있습니다. 함수 안의 길고 복잡한 코드를 정리하기 위해 중첩 함수를 사용할 수 있습니다.

``` swift
func returnFifteen() -> Int {    var y = 10    func add() {        y += 5    }    add()    return y}returnFifteen()
```

함수는 일급 타입(일급 객체)입니다. 이것은 함수가 반환 값으로 또 다른 함수를 반환할 수 있음을 의미합니다.

``` swift
func makeIncrementer() -> ((Int) -> Int) {
    func addOne(number: Int) -> Int {
        return 1 + number
    }
    return addOne
}
var increment = makeIncrementer()
increment(7)
```

함수는 전달인자의 하나로 다른 함수를 가질 수 있습니다.

``` swift
func hasAnyMatches(list: [Int], condition: (Int) -> Bool) -> Bool {
    for item in list {
        if condition(item) {
            return true
        }
    }
    return false
}
func lessThanTen(number: Int) -> Bool {
    return number < 10
}
var numbers = [20, 19, 7, 12]
hasAnyMatches(list: numbers, condition: lessThanTen)
```

함수는 사실 클로저의 특별한 경우입니다: 클로저는 나중에 호출될 수 있는 코드 블럭을 말합니다. 클로저 안의 코드는 클로저가 생성된 스코프 안에서 사용 가능한 변수와 함수 같은 것에 대한 접근권한을 가지고 있으며, 그것이 실행되었을 때 다른 스코프에 있더라도 마찬가지입니다 - 우리는 중첩 함수에서 이러한 예시를 본 바 있습니다. 클로저는 이름 없이 코드를 중괄호(`{}`)로 둘러쌈으로서 작성할 수 있습니다. 전달인자와 반환 타입을 코드 내용(body)으로부터 분리하기 위해 `in`을 사용하십시오.

(클로저를 선언한 시점과 사용한 시점이 다를 수 있다 - 함수도 마찬가지)

``` swift
numbers.map({ (number: Int) -> Int in
    let result = 3 * number
    return result
})
```

> 실험
>
> 모든 홀수에 대해 0을 반환하도록 클로저를 다시 작성해 보십시오.

클로저를 더 간결하게 작성하기 위한 몇 가지 선택 사항이 있습니다. 델리게이트(대리자)를 위한 콜백과 같이 클로저의 타입을 이미 알고 있을 때, 클로저의 매개변수나 리턴 타입 또는 둘 모두를 생략할 수 있습니다. 하나의 구문으로 이루어진 클로저는 암시적으로 그 구문의 값을 반환합니다.

``` swift
let mappedNumbers = numbers.map({ number in 3 * number })
print(mappedNumbers)
// Prints "[60, 57, 21, 36]"
```

매개변수를 이름 대신 숫자로 추론할 수도 있습니다 - 이 접근은 매우 짧은 클로저에서 특히 유용합니다. 함수의 마지막 전달인자로 전달된 클로저에 한 소괄호 뒤에 바로 나타낼 수 있습니다. 클로저가 함수의 유일한 전달인자일 때는 소괄호 양쪽을 생략할 수 있습니다.

``` swift
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
// Prints "[20, 19, 12, 7]"
```

### Objects and Classes

객체와 클래스.

클래스를 만들기 위해 `class`와 그 뒤에 클래스 이름을 사용하십시오. 클래스의 프로퍼티 선언은 클래스 맥락 안에 있다는 것만 제외하고는 상수나 변수 선언과 동일한 방식으로 작성됩니다. 비슷하게, 메서드와 함수 선언들도 동일한 방식으로 작성됩니다.

``` swift
class Shape {
    var numberOfSides = 0
    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```

> 실험
>
> `let` 으로 상수 프로퍼티를 추가하고, 전달인자를 받는 다른 메서드 하나를 추가해 보십시오.

클래스 이름 뒤에 소괄호를 붙임으로써 클래스의 인스턴스를 만드십시오. 인스턴스의 프로퍼티와 메서드에 접근하기 위해 점(`.`) 문법을 사용하십시오.

``` swift
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```

이 `Shape` 클래스의 버전은 어떤 중요한 것이 빠져 있습니다 : 그것은 인스턴스가 생성될 때 클래스를 준비하기 위한 생성자입니다. 생성자를 만들기 위해 `init`을 사용하십시오.

``` swift
class NamedShape {
    var numberOfSides: Int = 0
    var name: String

    init(name: String) {
        self.name = name
    }

    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```

`name` 프로퍼티와 생성자의 `name` 전달인자를 구별하기 위해 `self` 가 어떻게 사용되었는지에 주목하십시오. 클래스의 인스턴스를 만들 때 생성자를 위한 전달인자는 함수 호출처럼 전달됩니다. 모든 프로퍼티는 값이 할당될 필요가 있습니다 - 선언부(`numberOfSides`에서 그랬듯이) 또는 생성자(`name` 에서 그랬듯이) 중 한 곳에서 값이 반드시 할당되어야 합니다.

객체가 메모리에서 해제되기 전에 청소를 수행해야 한다면 디이니셜라이저(소멸자)를 만들기 위해 `deinit`을 사용하십시오.

하위 클래스는 자신의 클래스 이름 뒤에 콜론(`:`)으로 분리된 상위 클래스의 이름을 포함합니다. 클래스는 어떤 표준 루트 클래스도 상속하도록 요구하지 않습니다.* 따라서 필요한 대로 상위 클래스를 포함하거나 생략할 수 있습니다.

상위 클래스의 구현을 오버라이딩한 하위 클래스의 메서드는 `override`로 표시됩니다 - `override` 없이 실수로 오버라이딩한 메서드는 컴파일러 에러로 감지됩니다. 컴파일러는 상위 클래스에서 어떤 메서드도 오버라이딩하지 않는데 `override`가 붙어 있는 메서드 또한 감지합니다.

``` swift
class Square: NamedShape {
    var sideLength: Double

    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        numberOfSides = 4
    }

    func area() -> Double {
        return sideLength * sideLength
    }

    override func simpleDescription() -> String {
        return "A square with sides of length \(sideLength)."
    }
}
let test = Square(sideLength: 5.2, name: "my test square")
test.area()
test.simpleDescription()

```

> 실험
>
> `NamedShape`의 또 다른 하위 클래스인 `Circle`을 만들어 보십시오. 반지름을 가지고 생성자의 전달인자로서 이름을 가져야 합니다. `Circle`클래스의 메서드인 `area()` 와 `simpleDescription()`을 실행해 보십시오.

단순한 저장 프로퍼티에 더해서, 프로퍼티는 접근자(getter)와 설정자(setter)를 가질 수 있습니다.

``` swift
class EquilateralTriangle: NamedShape {
    var sideLength: Double = 0.0

    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        numberOfSides = 3
    }

    var perimeter: Double {
        get {
            return 3.0 * sideLength
        }
        set {
            sideLength = newValue / 3.0
        }
    }

    override func simpleDescription() -> String {
        return "An equilateral triangle with sides of length \(sideLength)."
    }
}
var triangle = EquilateralTriangle(sideLength: 3.1, name: "a triangle")
print(triangle.perimeter)
// Prints "9.3"
triangle.perimeter = 9.9
print(triangle.sideLength)
// Prints "3.3000000000000003"
```

`perimeter`의 설정자(setter)에서, 새로운 값은 `newValue`라는 암묵적 이름을 갖습니다. `set` 뒤의 소괄호 안에 명시적 이름을 지정할 수도 있습니다.

`EquilateralTriangle` 클래스의 생성자가 세 가지의 서로 다른 단계를 갖는 것에 주목하십시오 :

1. 하위 클래스가 선언한 프로퍼티의 값을 설정합니다. (`self.sideLength = sideLength`)
2. 상위 클래스의 생성자를 호출합니다. (`super.init(name:name)`)
3. 상위 클래스에 의해 정의된 프로퍼티의 값을 바꿉니다. 메서드/접근자(getter)/설정자(setter)를 사용하는 모든 추가적인 설정 작업 또한 이 시점에 이루어질 수 있습니다. (`numberOfSides = 3`)

만약 프로퍼티를 계산할 필요가 없지만 새로운 값을 설정하기 전이나 후에 실행되어야 할 코드가 있다면, `willSet` 과 `didSet` 을 사용하십시오. 당신이 설정한 코드는 생성자 밖에서 그 값이 변경될 때 마다 실행될 것입니다. 예를 들어, 아래의 클래스는 삼각형의 옆면의 길이가 언제나 사각형의 옆면의 길이와 같도록 보장합니다.

``` swift
class TriangleAndSquare {
    var triangle: EquilateralTriangle {
        willSet {
            square.sideLength = newValue.sideLength
        }
    }
    var square: Square {
        willSet {
            triangle.sideLength = newValue.sideLength
        }
    }
    init(size: Double, name: String) {
        square = Square(sideLength: size, name: name)
        triangle = EquilateralTriangle(sideLength: size, name: name)
    }
}
var triangleAndSquare = TriangleAndSquare(size: 10, name: "another test shape")
print(triangleAndSquare.square.sideLength)
// Prints "10.0"
print(triangleAndSquare.triangle.sideLength)
// Prints "10.0"
triangleAndSquare.square = Square(sideLength: 50, name: "larger square")
print(triangleAndSquare.triangle.sideLength)
// Prints "50.0"
```

옵셔널 값을 다룰 때는, 메서드/프로퍼티/서브스크립트와 같은 작업 앞에 `?` 을 사용할 수 있습니다. 만약 `?` 앞의 값이 nil이라면, `?` 뒤의 모든 것은 무시되고 그 표현식의 모든 값은 nil이 됩니다. 만약 그렇지 않으면, 옵셔널의 값이 벗겨지고 `?`뒤의 모든 것이 벗겨진 값으로서 실행됩니다. 두 경우 모두에서 전체 표현식의 값(`sideLength`)은 옵셔널 값입니다.

```swift
let optionalSquare: Square? = Square(sideLength: 2.5, name: "optional square")
let sideLength = optionalSquare?.sideLength
```

### Enumerations and Structures

열거형과 구조체

열거형을 만들기 위해 `enum`을 사용하십시오. 클래스와 다른 지정된 타입들처럼, 열거형도 연관된 메서드를 가질 수 있습니다.

``` swift
enum Rank: Int {
    case ace = 1
    case two, three, four, five, six, seven, eight, nine, ten
    case jack, queen, king

    func simpleDescription() -> String {
        switch self {
        case .ace:
            return "ace"
        case .jack:
            return "jack"
        case .queen:
            return "queen"
        case .king:
            return "king"
        default:
            return String(self.rawValue)
        }
    }
}
let ace = Rank.ace
let aceRawValue = ace.rawValue
```

> 실험
>
> 원시값을 비교함으로써 두 `Rank` 값을  비교하는 메서드를 작성해 보십시오.

기본적으로, 스위프트는 원시값을 0부터 하나씩 증가하는 값으로 할당합니다. 하지만 특정 값을 명시적으로 지정함으로써 이 동작을 바꿀 수 있습니다. 위의 예시에서, `Ace`는 명시적으로 1의 원시값을 가지며, 나머지의 원시값은 순서대로 할당되었습니다. 또한 열거형의 원시값으로 문자열이나 부동소수점 숫자를 사용할 수도 있습니다. 열거형 케이스의 원시값에 접근하기 위해 `rawValue` 프로퍼티를 사용하십시오.

원시값으로부터 열거형의 인스턴스를 만들기 위해 `init?(rawValue:)` 생성자를 사용하십시오. 원시값에 맞는 케이스가 있다면 그 열거형을 반환하거나, 맞는 케이스가 없다면 nil을 반환합니다.

``` swift
if let convertedRank = Rank(rawValue: 3) {
    let threeDescription = convertedRank.simpleDescription() // three
}
```

열거형의 케이스 값은 실제 값이며, 원시값을 다른 방식으로 작성한 것이 아닙니다. 사실, 의미 있는 원시값이 없는 케이스에는 원시값을 반드시 지정하지 않아도 됩니다.

``` swift
enum Suit {
    case spades, hearts, diamonds, clubs

    func simpleDescription() -> String {
        switch self {
        case .spades:
            return "spades"
        case .hearts:
            return "hearts"
        case .diamonds:
            return "diamonds"
        case .clubs:
            return "clubs"
        }
    }
}
let hearts = Suit.hearts
let heartsDescription = hearts.simpleDescription()
```

> 실험
>
> spades와 clubs에 대해 "black"을, hearts와 diamonds에 대해 "red"를 반환하는 `Suit`의 메서드 `color()` 를 추가하십시오.

위처럼 열거형의 `hearts` 케이스가 두 방식으로 추론됨을 주목하십시오. `hearts` 상수에 값을 할당할 때, 열거형 케이스 `Suit.hearts`는 그것의 전체 이름으로 추론됩니다. 왜냐하면 상수가 지정된 명시적 타입이 없기 때문입니다. switch문에서는, 열거형의 케이스는 `.hearts`라는 축약된 형태로 추론됩니다. 왜냐하면 `self`의 값이 이미 `Suit`라고 알려져 있기 때문입니다. 값의 타입이 이미 알려져 있다면 언제나 축약된 형태를 사용할 수 있습니다.

만약 열거형이 원시값을 가지고 있다면, 그 값들은 선언의 일부로 결정됩니다. 이는 특정 열거형 케이스의 모든 인스턴스가 항상 같은 원시값을 가짐을 의미합니다. 열거형 케이스에 대한 또 다른 선택은 케이스와 연관된 값(연관값)을 가지게 하는 것입니다 - 이 값들은 인스턴스를 만들 때 결정되며, 열거형 케이스의 인스턴스마다 다른 값을 가질 수 있습니다. 연관값은 열거형 케이스 인스턴스의 저장 프로퍼티와 같이 동작한다고 생각할 수 있습니다. 예를 들어, 서버로부터 일출과 일몰 시간을 요청하는 경우를 고려해 보십시오. 서버는 요청받은 정보를 응답하거나, 잘못되었을 때의 설명을 응답할 수 있습니다.

``` swift
enum ServerResponse {
    case result(String, String)
    case failure(String)
}

let success = ServerResponse.result("6:00 am", "8:09 pm")
let failure = ServerResponse.failure("Out of cheese.")

switch success {
case let .result(sunrise, sunset): // 열거형의 연관값을 사용하기 위해 case let 사용하고 그 이름을 부여함
    print("Sunrise is at \(sunrise) and sunset is at \(sunset).")
case let .failure(message):
    print("Failure...  \(message)")
}
// Prints "Sunrise is at 6:00 am and sunset is at 8:09 pm."
```

> 실험
>
> `ServerResponse`와 switch 문에 세 번째 케이스를 추가해 보십시오.

switch 케이스에 대해 맞는 값의 일부로서 일출과 일몰 시간이  `ServerResponse` 값으로부터 어떻게 추출되었는지 주목하십시오.

구조체를 만들기 위해  `struct`를 사용하십시오. 구조체는 메서드와 생성자를 포함해 클래스처럼 많은 같은 동작을 지원합니다. 구조체와 클래스의 가장 중요한 차이점 중 하나는, 구조체는 코드에서 전달될 때 항상 복사되지만, 클래스는 참조로 전달된다는 것입니다.

``` swift
struct Card {
    var rank: Rank
    var suit: Suit
    func simpleDescription() -> String {
        return "The \(rank.simpleDescription()) of \(suit.simpleDescription())"
    }
}
let threeOfSpades = Card(rank: .three, suit: .spades)
let threeOfSpadesDescription = threeOfSpades.simpleDescription(
```

> 실험
>
> 카드 한 장 마다 Rank와 Suit의 조합을 갖는 모든 카드 덱의 배열을 반환하는 함수를 작성해 보십시오.


### Protocols and Extensions

프로토콜과 익스텐션

프로토콜을 선언하기 위해 `protocol`을 사용하십시오.

``` swift
protocol ExampleProtocol {
    var simpleDescription: String { get }
    mutating func adjust()
}
```

클래스, 열거형, 구조체 모두가 프로토콜을 채택할 수 있습니다.

``` swift
class SimpleClass: ExampleProtocol {
    var simpleDescription: String = "A very simple class."
    var anotherProperty: Int = 69105
    func adjust() {
        simpleDescription += "  Now 100% adjusted."
    }
}
var a = SimpleClass()
a.adjust()
let aDescription = a.simpleDescription

struct SimpleStructure: ExampleProtocol {
    var simpleDescription: String = "A simple structure"
    mutating func adjust() {
        simpleDescription += " (adjusted)"
    }
}
var b = SimpleStructure()
b.adjust()
let bDescription = b.simpleDescription
```

> 실험
>
> `ExampleProtocol`에 또다른 요건을 추가하십시오. 여전히 프로토콜을 따르기 위해 `SimpleClass` 와 `SimpleStructure`를 만들 때 어떤 변화가 필요합니까?

`SimpleStructure`의 선언에 구조체를 수정하는 메서드를 표시하기 위해 `mutating`키워드를 사용한 것을 주목하십시오. `SimpleClass`선언의 메서드에는 mutating과 같은 어떤 표시도 필요하지 않습니다. 왜냐하면 클래스의 메서드는 항상 그 클래스를 수정하기 때문입니다.

존재하는 타입에 새로운 메서드나 연산 프로퍼티와 같은 기능을 추가하기 위해 `extension`을 사용하십시오. 다른 곳에서 선언되었거나 라이브러리 또는 프레임워크에서 불러온 타입에 프로토콜 일치를 추가하기 위해 익스텐션을 사용할 수 있습니다.

``` swift
extension Int: ExampleProtocol {
    var simpleDescription: String {
        return "The number \(self)"
    }
    mutating func adjust() {
        self += 42
    }
}
print(7.simpleDescription)
// Prints "The number 7"
```

> 실험
>
> Double타입에 absoluteValue 프로퍼티를 추가하는 익스텐션을 작성해 보십시오.

다른 이름 있는 타입들과 마찬가지로 프로토콜 이름을 사용할 수 있습니다. 예를 들어, 한 프로토콜을 따르지만 다른 타입들을 가진 객체들의 컬렉션을 만들기 위해서 프로토콜 이름을 사용할 수 있습니다. 타입이 프로토콜 타입인 값을 다룰 때는, 프로토콜 밖의 메서드 선언은 사용할 수 없습니다.

``` swift
let protocolValue: ExampleProtocol = a
print(protocolValue.simpleDescription)
// Prints "A very simple class.  Now 100% adjusted."
// print(protocolValue.anotherProperty)  // Uncomment to see the error

// 프로토콜 타입인 값으로 프로토콜 자체를 넣을 순 없고, 그 프로토콜을 채택한 객체가 올 수 있다.
// ExampleProtocol을 준수했다면 a 대신 다른 대상도 할당될 수 있다.
// 하지만 protocolValue는 ExampleProtocol타입이기 때문에 프로토콜에 정의된 요건들만 사용할 수 있다.
```

변수 `protocolValue` 가 실행 시점에 `SimpleClass` 타입을 가짐에도 불구하고, 컴파일러는 그것을 `ExampleProtocol`의 정해진 타입으로 다룹니다. 이것은 당신이 우연히라도 프로토콜 요건 외에 클래스가 구현한 메서드나 프로퍼티에 접근할 수 없음을 의미합니다.



### Error Handling

에러 처리

`Error` 프로토콜을 채택하는 어떤 타입이든 사용하여 에러를 나타낼 수 있습니다.

``` swift
enum PrinterError: Error {
    case outOfPaper
    case noToner
    case onFire
}
```

에러를 던지기 위해 `throw`를, 그리고 에러를 던질 수 있는 함수를 표시하기 위해 `throws`를 사용하십시오. 만약 함수에서 에러를 던진다면, 그 함수는 즉시 반환되며 그 함수를 호출한 코드에서 에러를 다루게 됩니다.

``` swift
func send(job: Int, toPrinter printerName: String) throws -> String {
    if printerName == "Never Has Toner" {
        throw PrinterError.noToner
    }
    return "Job sent"
}
```

에러를 다루기 위한 몇 가지 방법이 있습니다. 하나는 `do-catch` 를 사용하는 것입니다. `do` 블럭 내에서, `try`를 앞에 작성함으로써 에러를 던질 수 있는 코드를 표시합니다. `catch`블럭 내에서, 에러는 다른 이름을 주지 않는 이상 자동적으로 `error`라는 정해진 이름 됩니다.

``` swift
do {
    let printerResponse = try send(job: 1040, toPrinter: "Bi Sheng")
    print(printerResponse)
} catch {
    print(error)
}
// Prints "Job sent"
```

> 실험
>
> `send(job:toPrinter:)`함수가 에러를 던지도록 프린터의 이름을 "Never Has Toner"로 바꿔 보십시오.

특정 에러를 다루기 위해 여러 개의 `catch` 블럭을 사용할 수 있습니다. switch문에서 `case`뒤에 패턴을 사용하는 것처럼, `catch`뒤에도 패턴을 사용할 수 있습니다.

```swift
do {
    let printerResponse = try send(job: 1440, toPrinter: "Gutenberg")
    print(printerResponse)
} catch PrinterError.onFire {
    print("I'll just put this over here, with the rest of the fire.")
} catch let printerError as PrinterError {
    print("Printer error: \(printerError).")
} catch {
    print(error)
}
// Prints "Job sent"
```

> 실험
>
> `do` 블럭 내에 에러를 던지는 코드를 추가해 보십시오. 에러가 첫 번째 catch블럭에서 처리되기 위해 어떤 에러를 던져야 합니까? 두 번째와 세 번째 블럭은 어떠합니까?

에러를 처리하는 또 다른 방법은 결과를 옵셔널로 바꾸기 위해 `try?`를 사용하는 것입니다. 만약 함수가 에러를 던진다면, 특정 에러는 버려지며 그 결과는 nil이 됩니다. 그렇지 않다면, 그 결과는 함수가 반환한 값을 담은 옵셔널이 됩니다.

``` swift
let printerSuccess = try? send(job: 1884, toPrinter: "Mergenthaler")
let printerFailure = try? send(job: 1885, toPrinter: "Never Has Toner")
```

함수가 반환되기 직전에, 모든 다른 코드가 실행된 다음 실행되는 코드 블럭을 작성하기 위해 `defer`를 사용하십시오. 이 코드는 그 함수가 에러를 던지는지 여부와 관계없이 실행됩니다. 당신은 심지어 그것들이 다른 시점에 실행되어야 하더라도, 설정 및 정리 코드를 나란히 작성하기 위해 `defer`를 사용할 수 있습니다, 

``` swift
var fridgeIsOpen = false
let fridgeContent = ["milk", "eggs", "leftovers"]

func fridgeContains(_ food: String) -> Bool {
    fridgeIsOpen = true
    defer {
        fridgeIsOpen = false
    }

    let result = fridgeContent.contains(food)
    return result
}
fridgeContains("banana")
print(fridgeIsOpen)
// Prints "false"
```


### Generics

제네릭

제네릭 함수나 타입을 만들기 위해 꺾쇠 괄호 안에 이름을 작성하십시오.

``` swift
func makeArray<Item>(repeating item: Item, numberOfTimes: Int) -> [Item] {
    var result: [Item] = []
    for _ in 0..<numberOfTimes {
        result.append(item)
    }
    return result
}
makeArray(repeating: "knock", numberOfTimes: 4)
```

함수와 메서드, 클래스, 열거형, 구조체의 제네릭 형태를 만들 수 있습니다.

``` swift
// Reimplement the Swift standard library's optional type
enum OptionalValue<Wrapped> {
    case none
    case some(Wrapped)
}
var possibleInteger: OptionalValue<Int> = .none
possibleInteger = .some(100)
```

코드 몸통(body) 바로 앞에 where를 사용해 요건 목록을 지정하십시오 - 예를 들어, 프로토콜을 구현하기 위한 타입을 요구하거나, 두 타입이 같기를 요구하거나, 클래스가 특정 상위 클래스를 갖도록 요구하기 위해 사용할 수 잆습니다.

``` swift
func anyCommonElements<T: Sequence, U: Sequence>(_ lhs: T, _ rhs: U) -> Bool
    where T.Element: Equatable, T.Element == U.Element
{
    for lhsItem in lhs {
        for rhsItem in rhs {
            if lhsItem == rhsItem {
                return true
            }
        }
    }
    return false
}
anyCommonElements([1, 2, 3], [3])
```

> 실험
>
> `anyCommonElements(_:_:)`함수가 어떤 두 시퀀스를 공통으로 갖는 요소의 배열을 반환하는 함수를 만들도록 수정하십시오.

`<T: Equatable>`을 작성하는 것은 `<T> ... where T: Equatable`을 작성하는 것과 같습니다.



---

# LANGUAGE GUIDE

## The Basics

스위프트는 iOS, macOS, watchOS, tvOS 애플리케이션 개발을 위한 새로운 프로그래밍 언어입니다. 그렇긴 하지만, 스위프트의 많은 부분들은 C나 Objective-C 개발 경험으로부터 익숙할 것입니다.

스위프트는 C 와 Objective-C의 핵심적인 타입을 고유의 버전으로 제공합니다. 이는 정수 값을 위해 `Int`를 , 부동소수점 값을 위해 `Double`과 `Float`를, 불리언 값을 위해 `Bool`을, 텍스트 데이터를 위해 `String`을 제공하는 것을 포함합니다. 스위프트는 또한 Collection Types에 서술된 것과 같이, 세 가지 주요 컬렉션 타입인 Array, Set, Dictionary의 강력한 버전을 제공합니다.

C와 같이, 스위프트도 값을 저장하고 참조하기 위해 이름을 식별함으로써 변수를 사용합니다. 또한 스위프트는 값이 바뀔 수 없는 변수를 광범위하게 사용합니다. 이것은 상수라고도 알려져 있으며, C의 상수보다 훨씬 더 강력합니다. 상수는 당신이 변할 필요가 없는 값을 다룬다는 의도로 코드를 더 안전하고 명확하게 만들기 위해 스위프트 전체에 걸쳐 사용됩니다.

친숙한 타입들에 더해, 스위프트는 튜플과 같이 Objective-C에서는 찾을 수 없는 발전된 타입들을 소개합니다. 튜플은 값을 묶어서 만들고 전달하는 것을 가능하게 합니다. 당신은 함수로부터 여러 값들을 반환하기 위해 하나의 복합적인 값으로서 튜플을 사용할 수 있습니다.

스위프트는 또한 값의 없음을 다루는 옵셔널 타입을 소개합니다. 옵셔널은 "값이 있고, 그것은 x와 같다" 또는 "값이 전혀 없다"를 의미합니다. 옵셔널을 사용하는 것은 Objective-C에서 nil을 포인터와 함께 사용하는 것과 비슷하지만, 옵셔널은 클래스 뿐 아니라 어느 타입에나 사용할 수 있습니다. 옵셔널은 Objective-C의 nil포인터보다 더 안전하고 표현적일 뿐만 아니라, 스위프트의 많은 강력한 특성들의 핵심입니다.

스위프트는 타입-안전(type-safe) 언어입니다. 이는 당신이 코드로 다루는 값의 타입이 명확하도록 언어가 돕는다는 것을 의미합니다. 만약 당신의 코드의 일부가 String을 요구한다면, 실수로 Int를 전달하지 않도록 타입 안전성(type-safety)이 막아 줄 것입니다. 마찬가지로, 타입 안전성은 String을 요구하는 코드에 우연히 옵셔널 String을 전달하는 것을 막아줍니다. 타입 안전성은 개발 프로세스에서 가능한 빠른 시점에 에러를 찾아내고 수정하는 것을 도와줍니다.

### Constants and Variables
상수와 변수

상수와 변수는 이름 (예를 들어 `maximumNumberOfLoginAttempts` 이나 `welcomeMessage`) 과 특정한 타입의 값 (예를 들어 숫자 `10` 이나 문자열 `"Hello"`)을 연관짓습니다. 상수의 값은 한 번 설정되면 바뀔 수 없는 반면, 변수는 추후에 다른 값으로 설정될 수 있습니다.

#### Declaring Constants and Variables
상수와 변수 선언

상수와 변수는 사용되기 전에 반드시 선언되어야 합니다. `let` 키워드로 상수를 선언하고 `var` 키워드로 변수를 선언하십시오. 여기에 유저가 만든 로그인 시도 횟수를 추적하는 데에 상수와 변수가 어떻게 사용될 수 있는지에 대한 예시가 있습니다 :

``` swift
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
```

이 코드는 이렇게 읽을 수 있습니다 : 

"`maximumNumberOfLoginAttempts`라는 새로운 상수 하나를 선언하고, 그 값을 `10`으로 한다. 그런 다음, `currentLoginAttempt`라는 새로운 변수 하나를 선언하고, 그 값을 `0`으로 한다."

이 예시에서, 허용된 로그인 시도의 최대 횟수는 상수로 선언되었으며, 그 이유는 최대 값은 절대 변하지 않기 때문입니다. 현재 로그인 시도 카운터는 변수로 선언되었으며, 그 이유는 이 값은 로그인 시도가 실패할 때 마다 반드시 증가할 것이기 때문입니다.

쉼표로 구분하여 여러 개의 변수 또는 여러 개의 상수를 한 줄에 선언할 수 있습니다 :

``` swift
var x = 0.0, y = 0.0, z = 0.0
```

> 노트
>
> 만약 당신의 코드에서 저장된 값이 바뀌지 않을 것이라면, 항상 `let` 키워드와 함께 상수로 선언하십시오. 오직 바뀔 수 있어야 하는 값을 저장할 때만 변수를 사용하십시오.

#### Type Annotations
타입 어노테이션 (타입 명시)

상수 또는 변수가 저장할 수 있는 값의 유형을 명확히 하기 위해, 상수 또는 변수를 선언할 때 타입 어노테이션을 사용할 수 있습니다. 상수 또는 변수의 이름 뒤에 콜론(`:`)과 띄어쓰기, 사용할 타입의 이름을 작성함으로써 타입 어노테이션을 사용하십시오.
이 예시는 이 변수가 `String`값을 저장할 수 있음을 나타내기 위해,  `welcomeMessage`라는 이름의 변수에 대해 타입 어노테이션을 제공합니다.
``` swift
var welcomeMessage: String
```
선언의 콜론은 "...는 ...타입이다"를 의미하며, 따라서 위의 코드는 다음과 같이 읽을 수 있습니다 : 
" `String`타입인 `welcomeMessage`라는 이름의변수를 선언한다"
"타입이 String인"이라는 구절은 "어떤 String값도 담을 수 있는"을 의미합니다. 저장될 수 있는 대상의 타입 (또는 대상의 종류)를 의미한다고 생각하십시오.
`welcomeMessage` 변수는 에러 없이 어떤 문자열 값으로도 지정될 수 있습니다.
``` swift
welcomeMessage = "Hello"
```
동일한 타입의 여러 개의 관련된 변수를 한 줄로 정의할 수 있으며, 콤마(`,`)로 구분하고 마지막 변수명 뒤에 타입 어노테이션을 붙이면 됩니다.
``` swift
var red, green, blue: Double
```
> 노트  
> 실제로 타입 어노테이션을 작성해야 할 필요는 거의 없습니다. [타입 안전성과 타입 추론]([The Basics — The Swift Programming Language (Swift 5.5)](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322))에 설명된 것처럼, 만약 상수 또는 변수가 정의되는 시점에 초기값을 제공한다면 스위프트는 거의 항상 그 상수 또는 변수에서 사용될 타입을 추론합니다.  위의 `welcomeMessage` 예시에서, 초기값이 제공되지 않았고, 따라서 `welcomeMessage` 변수의 타입은 초기값으로부터 추론되기보다는 타입 어노테이션으로 구체화됩니다.  

#### Naming Constants and Variables
상수 및 변수명 짓기

상수와 변수의 이름은 유니코드 문자를 포함해 거의 모든 문자를 포함할 수 있습니다 : 
``` swift
let π = 3.14159
let 你好 = "你好世界"
let 🐶🐮 = "dogcow"
```
상수와 변수 이름은 공백문자, 수학 기호, 화살표, 전용 유니코드 스칼라 값, 선 그리기 또는 상자 그리기 문자를 포함할 수 없습니다. 또한 이름 안에 숫자를 포함할 수 있지만 숫자로 시작할 수는 없습니다.
한 번 상수나 변수를 특정 타입으로 선언하면, 같은 이름으로 다시 선언하거나 다른 타입의 값을 담도록 바꿀 수 없습니다. 또한 상수를 변수로 바꾸거나 변수를 상수로 바꿀 수도 없습니다.
> 노트  
> 만약 상수나 변수에 스위프트 키워드와 같은 이름을 사용해야 한다면, 그것을 이름으로 사용할 때 키워드를 백틱(`)으로 감싸십시오. 하지만, 다른 방법이 전혀 없지 않은 한 키워드를 이름으로 사용하는 것을 피하십시오.  
존재하는 변수의 값을 호환되는 타입의 다른 값으로 바꿀 수 있습니다. 이 예시에서, `friendlyWlecome`의 값은 `"Hello!"`에서 `"Bonjour!"`로 바뀌었습니다.
``` swift
var friendlyWelcome = "Hello!"
friendlyWelcome = "Bonjour!"
// friendlyWelcome is now "Bonjour!"
```
변수와 다르게, 상수의 값은 설정되고 난 뒤에는 바뀔 수 없습니다. 그렇게 바꾸기 위한 시도는 코드가 컴파일될 때 에러로 보고됩니다 :
``` swift
let languageName = "Swift"
languageName = "Swift++"
// This is a compile-time error: languageName cannot be changed.
```

#### Printing Constants and Variables
변수와 상수 출력하기

`print(_:separator:terminator:)` 함수로 현재의 상수 또는 변수의 값을 출력할 수 있습니다 :
``` swift
print(friendlyWelcome)
// Prints "Bonjour!"
```
`print(_:separator:terminator:)` 함수는 하나 또는 여러 값들을 적절한 산출물로 출력하는 전역 함수입니다. Xcode에서는, 예를 들면, `print(_:separator:terminator:)` 함수는 산출물을 Xcode의 "콘솔" 창에 출력합니다. `separator`와 `terminator` 매개변수는 기본값을 가지고 있으므로, 이 함수를 호출할 때 생략할 수 있습니다. 기본적으로, 이 함수는 출력하는 줄 끝에 줄바꿈 문자를 더해 끝냅니다. 값의 끝에 줄바꿈 문자를 빼고 출력하기 위해서는, `terminator`로 빈 문자열을 전달하십시오 - 예를 들어, `print(someValue, terminator: "")`. 기본값을 가진 매개변수에 대한 더 많은 정보를 위해서는, [Default Parameter Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID169) 를 참고하십시오.

스위프트는 변수 또는 상수의 이름을 더 긴 문자열에 플레이스홀더로 포함시키기 위해, 그리고 스위프트가 그것을 상수 또는 변수의 현재 값으로 대체하도록 하기 위해 *문자열 보간법*을 사용합니다. 이름을 소괄호로 감싸고, 여는 소괄호 앞에 백슬래시를 붙여 빠져나오십시오 : 
``` swift
print("The current value of friendlyWelcome is \(friendlyWelcome)")
// Prints "The current value of friendlyWelcome is Bonjour!"
```

> 노트  
> 문자열 보간법에 사용할 수 있는 모든 옵션들은  [String Interpolation](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html#ID292) 에 설명되어 있습니다.  


### Comments
주석

코드에 실행할 수 없는 텍스트를 포함시키기 위해 주석을 사용하십시오. 메모 또는 리마인더로 사용할 수 있습니다. 주석은 코드가 컴파일 될 때 스위프트 컴파일러에 의해 무시됩니다.
스위프트에서의 주석은 C언어의 주석과 매우 비슷합니다. 한 줄 주석은 두 개의 슬래시(`//`)로 시작합니다 :
``` swift
// This is a comment.
```
여러 줄 주석은 슬래시와 별표(`/*`)로 시작하고 별표와 슬래시(`*/`)로 끝납니다 :
``` swift
/* This is also a comment
but is written over multiple lines. */
```

C언어의 여러 줄 주석과 다르게, 스위프트의 여러 줄 주석은 다른 여러 줄 주석과 중첩될 수 있습니다. 중첩 주석은 여러 줄 주석을 열고, 두 번째 여러 줄 주석을 첫 번째 블럭 안에서 열어 작성합니다. 그 뒤 두 번째 블럭이 닫히고, 첫 번째 블럭이 계속됩니다.
``` swift
/* This is the start of the first multiline comment.
 /* This is the second, nested multiline comment. */
This is the end of the first multiline comment. */
```
여러 줄 중첩 주석은 큰 코드 블럭이 이미 여러 줄 주석으로 포함하고 있더라도, 빠르고 쉽게 주석 처리하는 것을 가능하게 해 줍니다.

### Semicolons
세미콜론

많은 다른 언어들과 다르게, 스위프트는 원한다면 쓸 수 있음에도 불구하고 코드의 각 구문 끝에 세미콜론(`;`)을 쓰도록 요구하지 않습니다. 하지만, 만약 한 줄에 여러 개의 구문을 적고 싶다면 세미콜론이 요구됩니다.
``` swift
let cat = "🐱"; print(cat)
// "🐱"를 출력합니다.
```

### Integers
정수형

정수형은 `42`나 `-23`처럼 분수의 구성 요소가 없는 모든 숫자입니다. 정수형은 부호가 있거나(양수, 0 또는 음수) 또는 부호가 없습니다(양수 또는 0).

 스위프트는 8, 16, 32, 64 비트 형태로 부호가 있는 정수형과 부호가 없는 정수형을 제공합니다. 이러한 정수형은 8비트의 부호가 없는 정수형을 `UInt8`, 32비트의 부호가 있는 정수형을 `Int32`라고 한다는 점에서 C언어와 비슷한 네이밍 컨벤션을 따릅니다. 스위프트의 다른 모든 타입들처럼, 이러한 정수형 타입은 대문자로 시작하는 이름을 갖습니다.

#### Integer Bounds
정수 경계

`min`과 `max` 프로퍼티로 각 정수 타입의 최소값과 최대값에 접근할 수 있습니다 :
``` swift
let minValue = UInt8.min  // minValue는 0과 같으며, 타입은 UInt8입니다.
let maxValue = UInt8.max  // maxValue는 255와 같으며, 타입은 UInt8입니다.
```
이 프로퍼티들의 값은 적절한 크기의 숫자 값을 가지며(위 예시의 `UInt8`과 같이), 그렇기 때문에 같은 타입의 다른 값 표현에 나란히 사용될 수 있습니다.

#### Int

대부분의 경우에, 코드에서 특정한 크기의 정수형을 고를 필요가 없습니다. 스위프트는 추가적으로 `Int`라는 정수 타입을 제공하며, 이 타입은 현재 플랫폼의 기본 단어 크기와 같은 크기를 갖습니다 : 
- 32비트 플랫폼에서, `Int`는 `Int32`와 같은 크기를 갖습니다.
- 64비트 플랫폼에서, `Int`는 `Int64`와 같은 크기를 갖습니다.
특정한 크기의 정수로 작업할 필요가 없는 한, 정수 값을 위해 항상 `Int`를 코드에 사용하십시오. 이것은 코드 일관성과 상호 운용성을 돕습니다. 심지어 32비트 플랫폼에서도, `Int`는  `-2,147,483,648` 와 
`2,147,483,647`  사이의 어떤 값이든 담을 수 있으며, 많은 정수 범위에 대해 충분히 큽니다.

#### UInt

스위프트는 `UInt`라는 부호가 없는 정수 타입도 제공하며, 현재 플랫폼의 기본 단어 크기와 같은 크기를 갖습니다 :
- 32비트 플랫폼에서, `UInt`는 `UInt32`와 같은 크기를 갖습니다.
- 64비트 플랫폼에서, `UInt`는 `UInt64`와 같은 크기를 갖습니다.

> 노트
> 오직 플랫폼의 기본 단어 크기와 같은 크기의 부호가 없는 정수 타입이 특별히 필요할 때만 `UInt`를 사용하십시오. 만약 그런 경우가 아니라면, `Int`가 선호되며, 심지어 저장되어야 할 값들이 음수가 될 수 없다고 알고 있는 경우에도 그러합니다.  [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322) 에 설명되어 있듯이, 정수 값에 대한 `Int`의 일관적인 사용은 코드 상호운용성을 돕고, 다른 숫자 타입끼리 변환할 필요가 없으며, 정수 타입 참조와도 맞습니다.

### Floating-Point Numbers
부동소수점 숫자
부동소수점 숫자는 `3.14159`, `0.1`, `-273.15`와 같이 분수 요소가 있는 숫자입니다.
부동소수점 타입은 정수 타입보다 훨씬 넓은 범위의 값을 나타낼 수 있으며, `Int`가 저장할 수 있는 것 보다 훨씬 크거나 작은 값을 저장할 수 있습니다. 스위프트는 두 개의 부호가 있는 부동소수점 숫자 타입을 제공합니다 :
- `Double`은 64비트의 부동소수점 숫자를 나타냅니다.
- `Float`는 32비트의 부동소수점 숫자를 나타냅니다.
> 노트
> `Float`의 정확도가 6개의 소수점 숫자만큼 작은 반면,  `Double`의 정확도는 최소 15개의 소수점 숫자를 가집니다. 사용할 적절한 부동소수점 타입은 코드에서 다뤄야 할 필요가 있는 값의 범위에 따라 달라집니다. 두 특성이 모두 적절할 수 있는 상황에서는, `Double`이 선호됩니다.

### Type Safety and Type Inference
스위프트는 *타입-안전* 언어입니다. 타입 안전 언어는 당신의 코드가 다루는 값의 타입이 명확해지도록 장려합니다. 만약 당신의 코드 일부가 String을 요구한다면, 그것에 실수로라도 Int를 전달할 수 없습니다.
스위프트가 타입 안전 언어이기 때문에, 코드를 컴파일할 때 *타입 체크*를 수행하며 일치하지 않는 타입은 에러로 표시합니다. 이것은 개발 프로세스에서 당신이 에러를 가능한 일찍 찾아내고 고칠 수 있도록 합니다.
타입 체크는 서로 다른 타입의 값을 다룰 때 에러를 피하도록 도와줍니다. 하지만, 이것은 당신이 선언하는 모든 상수와 변수의 타입을 명시해야 한다는 뜻은 아닙니다. 만약 필요한 값의 타입을 명시하지 않는다면, 스위프트는 적절한 타입을 계산하기 위해 *타입 추론*을 사용합니다. 타입 추론은 컴파일러가 당신의 코드를 컴파일할 때, 당신이 제공한 값을 간단히 검사함으로써 특정 표현의 타입을 자동으로 추론하도록 해 줍니다.

타입 추론 덕분에, 스위프트는 C언어나 Objective-C같은 언어보다 타입 선언을 훨씬 적게 요구합니다. 상수와 변수는 여전히 명시적으로 타입이 지정되어야 하지만, 타입을 특정해야 하는 작업의 대부분은 당신을 위해 작업이 완료됩니다.
타입 추론은 초기값이 있는 상수나 변수를 선언할 때 특히 유용합니다. 이것은 상수나 변수를 선언하는 시점에 리터럴 값 (또는 리터럴)을 할당함으로서 종종 수행됩니다. (리터럴 값은 아래 예시의 `42` 나 `3.14159` 처럼 소스 코드에 직접 나타난 값을 말합니다.)
예를 들어, 만약 새로운 상수에 42라는 리터럴 값을 할당하며 그것이 어떤 타입인지 지정하지 않으면, 스위프트는 당신이 그 상수가 Int가 되길 원했을 것이라고 추론합니다. 왜냐하면 당신이 정수형처럼 보이는 숫자로 그 상수를 초기화했기 때문입니다 :
``` swift
let meaningOfLife = 42
// meaningOfLife는 Int타입으로 추론됩니다.
```
마찬가지로, 만약 당신이 부동소수점 리터럴에 타입을 특정하지 않는다면, 스위프트는 당신이 Double을 만들고 싶었을 것이라고 추론합니다 :
``` swift
let pi = 3.14159
// pi는 Double타입으로 추론됩니다.
```
스위프트는 부동소수점 숫자의 타입을 추론할 때 (Float보다는) 항상 Double을 선택합니다.
만약 당신이 정수와 부동소수점 숫자를 조합해 표현한다면, 그 구문으로부터 Double 타입이 추론될 것입니다 :
``` swift
let anotherPi = 3 + 0.14159
// anotherPi 역시 Double타입으로 추론됩니다.
```
3이라는 리터럴 값은 그 자체로 명시된 타입이 없고, 그렇기 때문에 적절한 타입 추론 결과는 더해진 부분으로서의 부동소수점 리터럴의 존재로부터 Double이 됩니다.
