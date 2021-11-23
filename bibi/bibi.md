# The Swift Programming Language - Swift 5.5

> https://docs.swift.org/swift-book/#

**🐯 bibi가 해석한 문서입니다.**

---

## 목차

- [WELCOME TO SWIFT](#welcome-to-swift)
  * [About Swift](#about-swift)
  * [Version Compatibility](#version-compatibility)
  * [A Swift Tour](#a-swift-tour)
    + [Hello, world!](#hello--world-)
    + [Simple Values](#simple-values)
    + [Control Flow](#control-flow)
    + [Functions and Closures](#functions-and-closures)
- [LANGUAGE GUIDE](#language-guide)

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

### Hello, world!

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







---

# LANGUAGE GUIDE











