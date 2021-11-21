# A Swift Tour

<details>
	<summary>Outline</summary>

## [Outline](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html#:~:text=ON%20THIS%20PAGE-,A%20Swift%20Tour,-Tradition%20suggests%20that)

Tradition suggests that the first program in a new language should print the words “Hello, world!” on the screen. In Swift, this can be done in a single line:
```swift
print("Hello, world!")
// Prints "Hello, world!"
```
If you have written code in C or Objective-C, this syntax looks familiar to you—in Swift, this line of code is a complete program. You don’t need to import a separate library for functionality like input/output or string handling. Code written at global scope is used as the entry point for the program, so you don’t need a main() function. You also don’t need to write semicolons at the end of every statement.

This tour gives you enough information to start writing code in Swift by showing you how to accomplish a variety of programming tasks. Don’t worry if you don’t understand something—everything introduced in this tour is explained in detail in the rest of this book.

> NOTE
>
> For the best experience, open this chapter as a playground in Xcode. Playgrounds allow you to edit the code listings and see the result immediately.

---

## 개요

전통적으로 새로운 언어를 사용해서 작성하는 첫 번째 프로그램은 화면에 "Hello, world!"를 출력 하는 것이어야 합니다. 스위프트에서는 이것이 한 줄로 가능합니다:
```swift
print("Hello, world!")
// "Hello, world!" 출력
```
만약 당신이 C 혹은 오브젝트-C 를 사용하여 코드를 작성해 왔다면, 이런 구문은 익숙할 것입니다. 스위프트에서는 이 한 줄의 코드는 완성된 프로그램입니다. 입출력이나 문자열 처리를 위한 별도의 라이브러리를 임포트할 필요 없습니다. 전역 범위에서 쓰인 코드는 프로그램의 엔트리 포인트로 사용 되기 때문에, main() 함수가 필요 없습니다. 또한 모든 문장 뒤에 세미콜론을 붙일 필요도 없습니다. 

이 투어는 다양한 프로그래밍 과제를 해결하는 방법을 보여줌으로써 당신이 코딩을 시작하기에 충분한 정보를 줄 것입니다. 만약 이해하지 못한 것이 있더라도 걱정하지 마십시오. 이 투어에서 소개되는 모든 것들은 이 책의 나머지 부분에서 자세하게 설명할 것입니다. 

> 노트
>
> 최고의 경험을 하기 위해 Xcode의 플레이그라운드로 이 챕터를 여십시오. 플레이그라운드를 이용하여 코드 목록들을 편집하고 그 결과를 바로 볼 수 있습니다. 

---

_* — : dash (, 와 같은 의미)_</br>

---

</details>


<details>
<summary>Simple Values</summary>

## [Simple Values](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html#:~:text=Download%20Playground-,Simple%20Values,-Use%20let%20to)

Use let to make a constant and var to make a variable. The value of a constant doesn’t need to be known at compile time, but you must assign it a value exactly once. This means you can use constants to name a value that you determine once but use in many places.

```swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```

A constant or variable must have the same type as the value you want to assign to it. However, you don’t always have to write the type explicitly. Providing a value when you create a constant or variable lets the compiler infer its type. In the example above, the compiler infers that `myVariable` is an integer because its initial value is an integer.

If the initial value doesn’t provide enough information (or if isn’t an initial value), specify the type by writing it after the variable, separated by a colon.

```swift
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
```

> EXPERIMENT
>
> Create a constant with an explicit type of `Float` and a value of `4`.
>
> ```swift
> let a: Float = 4
> ```

Values are never implicitly converted to another type. If you need to convert a value to a different type, explicitly make an instance of the desired type.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

> EXPERIMENT
>
> Try removing the conversion to `String` from the last line. What error do you get?
>
> ```swift
> error: binary operator '+' cannot be applied to operands of type 'String' and 'Int'
> ```

There’s an even simpler way to include values in strings: Write the value in parentheses, and write a backslash (`\`) before the parentheses. For example:

```swift
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```

> EXPERIMENT
>
> Use `\()` to include a floating-point calculation in a string and to include someone’s name in a greeting.

Use three double quotation marks (`"""`) for strings that take up multiple lines. Indentation at the start of each quoted line is removed, as long as it matches the indentation of the closing quotation marks. For example:

```swift
let quotation = """
I said "I have \(apples) apples."
And then I said "I have \(apples + oranges) pieces of fruit."
"""
```

Create arrays and dictionaries using brackets (`[]`), and access their elements by writing the index or key in brackets. A comma is allowed after the last element.

```swift
var shoppingList = ["catfish", "water", "tulips"]
shoppingList[1] = "bottle of water"

var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```

Arrays automatically grow as you add elements.

```swift
shoppingList.append("blue paint")
print(shoppingList)
```

To create an empty array or dictionary, use the initializer syntax.

```swift
let emptyArray: [String] = []
let emptyDictionary: [String: Float] = [:]
```

If type information can be inferred, you can write an empty array as `[]` and an empty dictionary as `[:]`—for example, when you set a new value for a variable or pass an argument to a function.

```swift
shoppingList = []
occupations = [:]
```

---

## 간단한 값들

상수를 만들기 위해 `let` 을 사용하고, 변수를 만들기 위해 `var` 를 사용하십시오. 상수의 값은 컴파일 타임에 알고 있을 필요는 없지만, 무조건 한번, 그것에 값을 할당해 주어야 합니다. 즉, 당신은 상수를 한번 정해서 여러 군데에서 사용하는 값에 이름을 붙이기 위해 사용할 수 있습니다. 

```swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```

상수나 변수는 반드시 당신이 그것에 할당하고 싶은 값과 같은 타입을 가져야 합니다. 하지만, 항상 타입을 명시적으로 작성해야 하는 것은 아닙니다. 상수나 변수를 생성할 때 값을 제공하면, 컴파일러가 그 타입을 유추할 수 있습니다. 위의 예에서,  `myVariable` 의 초기값이 정수이기 때문에 컴파일러는 이것의 타입을 정수로 유추할 수 있습니다. 

만약 초기값이 충분한 정보를 주지 않거나 혹은 없다면, 변수 뒤에 콜론으로 구분하여 타입을 적어서 지정하십시오. 

```swift
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
```

> 실험
>
> `Float` 타입과  `4` 의 값을 가지는 상수를 생성하십시오.
>
> ```swift
> let a: Float = 4
> ```

값은 결코 암묵적으로 다른 타입으로 변환되지 않습니다. 만약 값을 다른 타입으로 변환해야 한다면, 요구되는 타입의 인스턴스를 명시적으로 만드십시오.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

> 실험
>
> 마지막 줄에서 `String` 으로 변환하는 것을 제거해 보십시오. 어떤 오류가 발생합니까?
>
> ```swift
> 오류: 이항 연산자 '+'는 'String'과 'Int' 타입의 피연산자에 적용할 수 없습니다.
> ```

문자열에 값을 넣는 더 쉬운 방법이 있습니다. 괄호 안에 값을 적고, 괄호 앞에 백슬래시(`\`) 를 적으십시오. 예를 들어:

```swift
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```

> 실험
>
> 문자열에 부동 소수점 계산을 넣고, 인사말에 누군가의 이름을 넣기 위해서 `\()` 를 사용하십시오.  

여러 줄을 차지하는 문자열에서는 세 개의 쌍따옴표 (`"""`) 를 사용하십시오. 닫는 따옴표의 들여쓰기와 일치하는 한, 각 줄의 시작 부분의 들여쓰기는 제거됩니다. 예를 들어:

```swift
let quotation = """
I said "I have \(apples) apples."
And then I said "I have \(apples + oranges) pieces of fruit."
"""
```

괄호 (`[]`)를 사용하여 배열과 딕셔너리를 만들고, 괄호 안에 인덱스나 키값을 적어서 그 인자들에 접근하십시오. 마지막 인자 뒤에 쉼표를 적어도 괜찮습니다. 

```swift
var shoppingList = ["catfish", "water", "tulips"]
shoppingList[1] = "bottle of water"

var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```

배열은 인자를 추가하는 만큼 자동으로 증가합니다. 

```swift
shoppingList.append("blue paint")
print(shoppingList)
```

빈 배열이나 딕셔너리를 만드려면, 초기화 구문을 사용하십시오.

```swift
let emptyArray: [String] = []
let emptyDictionary: [String: Float] = [:]
```

타입 정보를 유추할 수 있다면, 빈 배열을 `[]` 로 적을 수 있고, 빈 딕셔너리를 `[:]` 로 적을 수 있습니다. 예를 들어, 변수에 새로운 값을 설정하거나, 인수를 함수에 전달할 때입니다.

```swift
shoppingList = []
occupations = [:]
```

---

_\* specify: 지정하다, 기입하다, 명시하다_</br>
_\* explicit: 명백한</br>_
_\* implicitly: 암묵적으로</br>_
_\* binary operator: 이항 연산자</br>_
_\* operand: 피연산자</br>_
_\* parentheses: 괄호</br>_
_\* floating-point: 부동 소수점</br>_
_\* take up: 차지하다</br>_
_\* as long as: ~하는 한</br>_

---

</details>


<details>
<summary>Control Flow</summary>

## [Control Flow](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html#:~:text=occupations%20%3D%20%5B%3A%5D-,Control%20Flow,-Use%20if%20and)

Use `if` and `switch` to make conditionals, and use `for`-`in`, `while`, and `repeat`-`while` to make loops. Parentheses around the condition or loop variable are optional. Braces around the body are required.

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

In an `if` statement, the conditional must be a Boolean expression—this means that code such as `if score { ... }` is an error, not an implicit comparison to zero.

You can use `if` and `let` together to work with values that might be missing. These values are represented as optionals. An optional value either contains a value or contains `nil` to indicate that a value is missing. Write a question mark (`?`) after the type of a value to mark the value as optional.

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

> EXPERIMENT
>
> Change `optionalName` to `nil`. What greeting do you get? Add an `else` clause that sets a different greeting if `optionalName` is `nil`.
>
> ```swift
> var optionalName: String? = nil
> var greeting = "Hello!"
> if let name = optionalName {
>     greeting = "Hello, \(name)"
> } else {
>     greeting = "Hello, is anyone here?"
> }
> ```

If the optional value is `nil`, the conditional is `false` and the code in braces is skipped. Otherwise, the optional value is unwrapped and assigned to the constant after `let`, which makes the unwrapped value available inside the block of code.

Another way to handle optional values is to provide a default value using the `??` operator. If the optional value is missing, the default value is used instead.

```swift
let nickname: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickname ?? fullName)"
```

Switches support any kind of data and a wide variety of comparison operations—they aren’t limited to integers and tests for equality.

```swift
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

> EXPERIMENT
>
> Try removing the default case. What error do you get?
>
> ```swift
> error: switch must be exhaustive
> ```

Notice how `let` can be used in a pattern to assign the value that matched the pattern to a constant.

After executing the code inside the switch case that matched, the program exits from the switch statement. Execution doesn’t continue to the next case, so you don’t need to explicitly break out of the switch at the end of each case’s code.

You use `for`-`in` to iterate over items in a dictionary by providing a pair of names to use for each key-value pair. Dictionaries are an unordered collection, so their keys and values are iterated over in an arbitrary order.

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

> EXPERIMENT
>
> Replace the `_` with a variable name, and keep track of which kind of number was the largest.

Use `while` to repeat a block of code until a condition changes. The condition of a loop can be at the end instead, ensuring that the loop is run at least once.

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

You can keep an index in a loop by using `..<` to make a range of indexes.

```swift
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
// Prints "6"
```

Use `..<` to make a range that omits its upper value, and use `...` to make a range that includes both values.

---

## 제어 흐름

 `if` 와 `switch`를 사용하여 조건문을 만들고,  `for`-`in`, `while`, 과 `repeat`-`while` 을 사용하여 반복문을 만들 수 있습니다. 조건문과 반복문 변수를 괄호로 감싸는 것은 선택사항입니다. 바디는 반드시 중괄호로 감싸야 합니다. 

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
// "11" 출력
```

`if` 문에서 조건은 반드시 boolean 표현식이어야 합니다. 이것은 `if score { ... }` 같은 코드가 0에 대한 암묵적인 비교가 아니라 오류임을 의미합니다. 

없을지도 모르는 값을 사용하기 위해서 `if` 와 `let` 을 함께 사용할 수 있습니다. 이러한 값들을 옵셔널이라고 합니다. 옵셔널 값은 값을 포함하거나, 값이 없다는 것을 의미하는 `nil` 을 포함합니다. 값을 옵셔널로 표시하려면 값의 타입 뒤에 물음표 (`?`)를 적으십시오.

```swift
var optionalString: String? = "Hello"
print(optionalString == nil)
// "false" 출력

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
```

> 실험
>
> `optionalName` 을 `nil`로 바꾸십시오. 어떤 인사말을 얻습니까? `optionalName` 이 `nil`일 때 다른 인사말을 설정하는  `else` 절을 추가하십시오.
>
> ```swift
> var optionalName: String? = nil
> var greeting = "Hello!"
> if let name = optionalName {
>     greeting = "Hello, \(name)"
> } else {
>     greeting = "Hello, is anyone here?"
> }
> ```

옵셔널 값이 `nil` 이면, 조건은 `false` 이고 중괄호 안에 코드는 무시됩니다. 그렇지 않으면, 옵셔널 값은 언랩되고, `let` 뒤에서 상수로 할당되어 코드 블록 안에서 언랩된 값으로 사용할 수 있습니다. 

옵셔널 값을 다루는 다른 방법은 `??` 연산자를 사용하여 디폴트 값을 제공하는 것입니다. 만약 옵셔널 값이 없으면 디폴트 값이 대신 사용됩니다. 

```swift
let nickname: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickname ?? fullName)"
```

스위치문은 모든 종류의 데이터와 넓은 범위의 비교 연산자들을 지원합니다. 그들은 정수와 같은 것을 비교하는 것에 국한되지 않습니다. 

```swift
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
// "Is it a spicy red pepper?" 출력
```

> 실험
>
> 디폴트 경우를 제거해 보십시오. 어떤 에러가 생깁니까?
> ```swift
> 오류: switch는 반드시 완전해야 합니다.
> ```

패턴과 일치하는 값을 상수에 할당시키기 위한 패턴에서 `let` 이 어떻게 사용되는지 주목하십시오.

일치하는 switch case 내부의 코드가 실행된 후, 프로그램은 switch 문으로부터 탈출합니다. 다음 case로 연이어 실행되지 않기 때문에, 각 case 코드의 마지막에서 명시적으로 break를 할 필요 없습니다. 

딕셔너리에서 아이템을 반복하기 위해, 각각의 키-값 쌍을 사용하기 위한 이름 쌍을 제공함으로써 `for`-`in` 을 사용합니다. 딕셔너리는 순서가 없는 집합이기 때문에, 그 키와 값들은 임의의 순서로 반복됩니다. 

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
// "25" 출력
```

> EXPERIMENT
>
> `_`를 변수 이름으로 대체하고, 어떤 종류의 숫자가 가장 큰지 추적하십시오.

조건이 변경될 때까지 코드 블럭을 반복하기 위해 `while` 을 사용하십시오. 반복문의 조건은 마지막에 있을 수 있고, 그것은 반복이 최소한 한번 실행된다는 것을 보장해줍니다.

```swift
var n = 2
while n < 100 {
    n *= 2
}
print(n)
// "128" 출력

var m = 2
repeat {
    m *= 2
} while m < 100
print(m)
// "128" 출력
```

인덱스의 범위를 만드는 `..<` 를 사용하여 반복문의 인덱스를 유지시킬 수 있습니다. 

```swift
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
// "6" 출력
```

더 큰 값은 생략하는 범위를 만들려면 `..<` 을 사용하고, 양쪽 값을 포함하는 범위를 만들려면  `...` 을 사용하십시오.

---

_\* implicit: 절대적인, 함축적인, 암묵적인_</br>
_\* comparison: 비교</br>_
_\* clause: 절</br>_
_\* Otherwise: 그렇지 않으면_</br>
_\* make something available: ~을 사용할 수 있도록 해두다_</br>
_\* exhaustive: 철저한, 완전한, 포괄적인</br>_
_\* executing: 실행_</br>
_\* iterate over: 반복하다_</br>
_\* arbitrary: 임의의</br>_
_\* omit: 생략하다_</br>

---

</details>

<details>
	<summary>Functions and Closures</summary>

## [Functions and Closures](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html#:~:text=includes%20both%20values.-,Functions%20and%20Closures,-Use%20func%20to)

Use `func` to declare a function. Call a function by following its name with a list of arguments in parentheses. Use `->` to separate the parameter names and types from the function’s return type.

```swift
func greet(person: String, day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet(person: "Bob", day: "Tuesday")
```

> EXPERIMENT
>
> Remove the `day` parameter. Add a parameter to include today’s lunch special in the greeting.
>
> ```swift
> func greet(person: String, lunchSpecial: String) -> String {
>  return "Hello \(person), today's lunch special is \(lunchSpecial)."
> }
> greet(person: "Bob", lunchSpecial: "Steak")
> ```

By default, functions use their parameter names as labels for their arguments. Write a custom argument label before the parameter name, or write `_` to use no argument label.

```swift
func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

Use a tuple to make a compound value—for example, to return multiple values from a function. The elements of a tuple can be referred to either by name or by number.

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

Functions can be nested. Nested functions have access to variables that were declared in the outer function. You can use nested functions to organize the code in a function that’s long or complex.

```swift
func returnFifteen() -> Int {
    var y = 10
    func add() {
        y += 5
    }
    add()
    return y
}
returnFifteen()
```

Functions are a first-class type. This means that a function can return another function as its value.

```swift
func makeIncrementer() -> ((Int) -> Int) {
    func addOne(number: Int) -> Int {
        return 1 + number
    }
    return addOne
}
var increment = makeIncrementer()
increment(7)
```

A function can take another function as one of its arguments.

```swift
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

Functions are actually a special case of closures: blocks of code that can be called later. The code in a closure has access to things like variables and functions that were available in the scope where the closure was created, even if the closure is in a different scope when it’s executed—you saw an example of this already with nested functions. You can write a closure without a name by surrounding code with braces (`{}`). Use `in` to separate the arguments and return type from the body.

```swift
numbers.map({ (number: Int) -> Int in
    let result = 3 * number
    return result
})
```

> EXPERIMENT
>
> Rewrite the closure to return zero for all odd numbers.
>
> ```swift
> numbers.map({ (number: Int) -> Int in
>  return number % 2 == 0 ? number : 0
> })
> ```

You have several options for writing closures more concisely. When a closure’s type is already known, such as the callback for a delegate, you can omit the type of its parameters, its return type, or both. Single statement closures implicitly return the value of their only statement.

```swift
let mappedNumbers = numbers.map({ number in 3 * number })
print(mappedNumbers)
// Prints "[60, 57, 21, 36]"
```

You can refer to parameters by number instead of by name—this approach is especially useful in very short closures. A closure passed as the last argument to a function can appear immediately after the parentheses. When a closure is the only argument to a function, you can omit the parentheses entirely.

```swift
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
// Prints "[20, 19, 12, 7]"
```

---

## 함수와 클로저

`func` 를 사용하여 함수를 선언하십시오. 뒤이어 오는 그 이름과 괄호 안에 있는 인수 목록으로 함수를 호출하십시오. `->` 를 사용하여 매개변수의 이름과 타입을 함수의 반환 타입과 분리시키십시오.

```swift
func greet(person: String, day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet(person: "Bob", day: "Tuesday")
```

> 실험
>
> 매개변수 `day` 를 지우십시오. 인사말에 오늘의 점심 스페셜을 포함시키기 위해 매개변수를 추가하십시오.
>
> ```swift
> func greet(person: String, lunchSpecial: String) -> String {
>  return "Hello \(person), today's lunch special is \(lunchSpecial)."
> }
> greet(person: "Bob", lunchSpecial: "Steak")
> ```

기본적으로 함수는 매개변수 이름을 인수의 라벨로 사용합니다. 매개변수 이름 앞에 커스텀 인수 라벨을 적거나, `_` 를 사용하여 인수 라벨을 사용하지 않을 수 있습니다. 

```swift
func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

튜플을 사용하여 값 복합체를 만드십시오. 예를 들어, 함수로 부터 여러개의 값을 반환받기 위한 경우입니다. 튜플의 요소들은 이름이나 번호로 참조할 수 있습니다. 

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
// "120" 출력
print(statistics.2)
// "120" 출력
```

함수는 중첩될 수 있습니다. 중첩된 함수는 외부에서 선언된 변수에 대한 접근 권한을 가집니다. 길거나 복잡한 함수의 코드를 구성하기 위해서 중첩된 함수를 사용할 수 있습니다. 

```swift
func returnFifteen() -> Int {
    var y = 10
    func add() {
        y += 5
    }
    add()
    return y
}
returnFifteen()
```

함수는 일급 시민입니다. 이 말은 함수가 다른 함수를 그것의 값으로써 반환할 수 있다는 것을 의미합니다. 

```swift
func makeIncrementer() -> ((Int) -> Int) {
    func addOne(number: Int) -> Int {
        return 1 + number
    }
    return addOne
}
var increment = makeIncrementer()
increment(7)
```

함수는 다른 함수를 그것의 인수 중 하나로 가질 수 있습니다. 

```swift
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

사실 함수는 클로저의 특별한 한 종류입니다. 클로저는 이후에 호출 할 수 있는 코드 블럭입니다. 클로저의 코드는 실행 환경과 상관없이, 클로저가 처음 생성된 환경에서 접근 가능했던 변수와 함수 같은 것들에 접근할 수 있습니다. 이것의 예를 이미 중첩 함수에서 봤습니다. 중괄호(`{}`)로 코드를 감싸서 이름 없이 클로저를 작성할 수 있습니다. `in` 을 사용하여 인수와 반환 타입을 몸통으로 부터 분리시키십시오.

```swift
numbers.map({ (number: Int) -> Int in
    let result = 3 * number
    return result
})
```

> 실험
>
> 모든 홀수에 대해 0을 반환하도록 클로저를 다시 작성하십시오.
>
> ```swift
> numbers.map({ (number: Int) -> Int in
>  return number % 2 == 0 ? number : 0
> })
> ```

클로저를 더 간결하게 작성하는 여러가지 방법이 있습니다. 델리게이트의 콜백 같이 클로저의 타입을 이미 알고 있는 경우에는 변수의 타입과 반환 타입, 혹은 둘 다를 생략할 수 있습니다. 한 줄 짜리 클로저는 암묵적으로 오직 그 줄의 값을 반환합니다.

```swift
let mappedNumbers = numbers.map({ number in 3 * number })
print(mappedNumbers)
// "[60, 57, 21, 36]" 출력
```

이름 대신 번호를 통해 변수를 참조할 수 있습니다. 이런 식의 접근은 매우 짧은 클로저에서 특히 유용합니다. 함수에 마지막 인자로 전달된 클로저는 괄호 뒤에 바로 나타날 수 있습니다. 클로저가 함수의 유일한 인수일 때는 괄호를 완전히 생략할 수 있습니다. 

```swift
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
// "[20, 19, 12, 7]" 출력
```

---

_* refer: 참조하다_</br>
_* nest: 중첩하다_</br>
_* concisely: 간결하게_</br>

---

</details>

<details>
	<summary>Objects and Classes</summary>

## [Objects and Classes](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html#:~:text=19%2C%2012%2C%207%5D%22-,Objects%20and%20Classes,-Use%20class%20followed)

Use `class` followed by the class’s name to create a class. A property declaration in a class is written the same way as a constant or variable declaration, except that it’s in the context of a class. Likewise, method and function declarations are written the same way.

```swift
class Shape {
	var numberOfSides = 0
    func simpleDescription() -> String {
	    return "A shape with \(numberOfSides) sides."
    }
}
```

> EXPERIMENT
>
> Add a constant property with `let`, and add another method that takes an argument.

Create an instance of a class by putting parentheses after the class name. Use dot syntax to access the properties and methods of the instance.

```swift
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```

This version of the `Shape` class is missing something important: an initializer to set up the class when an instance is created. Use `init` to create one.

```swift
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

Notice how `self` is used to distinguish the `name` property from the `name` argument to the initializer. The arguments to the initializer are passed like a function call when you create an instance of the class. Every property needs a value assigned—either in its declaration (as with `numberOfSides`) or in the initializer (as with `name`).

Use `deinit` to create a deinitializer if you need to perform some cleanup before the object is deallocated.

Subclasses include their superclass name after their class name, separated by a colon. There’s no requirement for classes to subclass any standard root class, so you can include or omit a superclass as needed.

Methods on a subclass that override the superclass’s implementation are marked with `override`—overriding a method by accident, without `override`, is detected by the compiler as an error. The compiler also detects methods with `override` that don’t actually override any method in the superclass.

```swift
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

> EXPERIMENT
>
> Make another subclass of `NamedShape` called `Circle` that takes a radius and a name as arguments to its initializer. Implement an `area()` and a `simpleDescription()` method on the `Circle` class.

In addition to simple properties that are stored, properties can have a getter and a setter.

```swift
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

In the setter for `perimeter`, the new value has the implicit name `newValue`. You can provide an explicit name in parentheses after `set`.

Notice that the initializer for the `EquilateralTriangle` class has three different steps:

1. Setting the value of properties that the subclass declares.
2. Calling the superclass’s initializer.
3. Changing the value of properties defined by the superclass. Any additional setup work that uses methods, getters, or setters can also be done at this point.

If you don’t need to compute the property but still need to provide code that’s run before and after setting a new value, use `willSet` and `didSet`. The code you provide is run any time the value changes outside of an initializer. For example, the class below ensures that the side length of its triangle is always the same as the side length of its square.

```swift
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

When working with optional values, you can write `?` before operations like methods, properties, and subscripting. If the value before the `?` is `nil`, everything after the `?` is ignored and the value of the whole expression is `nil`. Otherwise, the optional value is unwrapped, and everything after the `?` acts on the unwrapped value. In both cases, the value of the whole expression is an optional value.

```swift
let optionalSquare: Square? = Square(sideLength: 2.5, name: "optional square")
let sideLength = optionalSquare?.sideLength
```

---

## 객체와 클래스

`class` 뒤에 클래스의 이름을 붙여 클래스를 생성합니다. 클래스에서 속성은 클래스 내부에서라는 것만 제외하면, 상수나 변수와 같은 방식으로 선언됩니다. 마찬가지로, 메소드와 함수 또한 같은 방식으로 선언됩니다. 

```swift
class Shape {
	var numberOfSides = 0
    func simpleDescription() -> String {
	    return "A shape with \(numberOfSides) sides."
    }
}
```

> 실험
>
> `let` 을 사용하여 상수 속성을 추가하고, 인수를 가지는 메소드를 추가하십시오.

클래스의 이름 뒤에 괄호를 넣어서 클래스의 인스턴스를 생성합니다. 점 구문을 사용하여 인스턴스의 속성과 메소드에 접근할 수 있습니다. 

```swift
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```

이 버전의 `Shape` 클래스는 인스턴스가 생성될 때 클래스를 설정하기 위한 생성자라는 중요한 무언가가 빠져 있습니다. `init` 을 사용하여 생성합니다. 

```swift
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

생성자의 인수 `name` 과 속성 `name` 을 구분하기 위해 `self` 가 어떻게 사용되는지에 주목하십시오. 클래스의 인스턴스를 생성할 때, 생성자의 인수는 함수 호출처럼 전달됩니다. 모든 속성에는 값이 할당되어야 합니다. `numberOfSides` 처럼 선언에서 던지, `name` 처럼 생성자에서 던지. 

객체가 할당 해제되기 전에 약간의 정리가 필요하다면 `deinit` 을 사용하여 디이니셜라이저를 생성합니다.

서브 클래스는 클래스 이름뒤에 콜론으로 구분하여 그들의 슈퍼 클래스의 이름을 포함합니다. 클래스가 어떤 표준 루트 클래스의 하위로 분류될 필요는 없기 때문에, 필요에 따라 슈퍼 클래스를 포함하거나 생략할 수 있습니다. 

슈퍼 클래스의 구현을 재정의한 서브 클래스의 메소드는 `override` 로 표시됩니다. `override` 없이 우연히 메소드를 재정의 하면 컴파일러가 오류로 감지합니다. 또한, `override` 를 사용했지만 실제로는 슈퍼 클래스로의 어떠한 메소드도 재정의한 것이 아니라면 컴파일러가 감지합니다. 

```swift
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
> 생성자에 반지름과 이름을 인수로 가지는, `Circle` 이라는 `NamedShape` 의 또 다른 서브 클래스를 생성하십시오. `Circle` 클래스에 `area()` 메소드와 `simpleDescription()` 메소드를 구현하십시오.

프로퍼티는 단순한 저장 뿐만 아니라, 게터와 세터를 가질 수 있습니다. 

```swift
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
// "9.3" 출력
triangle.perimeter = 9.9
print(triangle.sideLength)
// "3.3000000000000003" 출력
```

`perimeter` 의 세터에서 새로운 값은 암묵적으로 `newValue` 라는 이름을 가집니다. `set` 뒤의 괄호 안에 명시적인 이름을 줄 수도 있습니다. 

`EquilateralTriangle` 클래스의 생성자가 가지고 있는 세가지 다른 단계를 주목하십시오:

1. 서브 클래스가 선언한 속성의 값들을 설정합니다.
2. 서브 클래스의 생성자를 호출합니다.
3. 슈퍼 클래스에서 정의된 속성의 값들을 변경합니다. 메소드, 게터, 혹은 세터를 사용하는 여러 추가적인 설정 작업들 또한 이 시점에 모두 완료할 수 있습니다.

만약 속성을 계산할 필요는 없지만, 여전히 새로운 값을 설정하기 전이나 후에 실행되는 코드를 제공해야 한다면, `willSet` 과 `didSet` 을 사용하십시오. 제공한 코드는 생성자 외부에서 값이 변화할 때마다 실행됩니다. 예를 들어, 아래에 있는 클래스는 삼각형의 빗변의 길이와 사각형의 빗변의 길이가 항상 같다는 것을 보증해줍니다. 

```swift
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
// "10.0" 출력
print(triangleAndSquare.triangle.sideLength)
// "10.0" 출력
triangleAndSquare.square = Square(sideLength: 50, name: "larger square")
print(triangleAndSquare.triangle.sideLength)
// "50.0" 출력
```

옵셔널 값을 사용할 때, 메소드, 속성, 그리고 서브스크립팅 같은 작업들 앞에 `?` 를 사용할 수 있습니다. `?` 앞의 값이 `nil` 이면, `?` 뒤의 모든 것들을 무시하고 그 전체 표현식 또한 `nil` 입니다. 그게 아니라 옵셔널 값이 언랩 됐다면 `?` 뒤의 모든 것들은 그 언랩된 값에 대해 실행됩니다. 두 경우 모두 전체 표현식의 값은 옵셔널 값입니다. 

```swift
let optionalSquare: Square? = Square(sideLength: 2.5, name: "optional square")
let sideLength = optionalSquare?.sideLength
```

---

_* deallocate : 할당 해제하다_</br>
_* implementation : 구현_</br>
_* In addition to : 게다가, 뿐만 아니라_</br>
_* perimeter : 둘레_</br>

---

</details>

<details>
	<summary>Enumerations and Structures</summary>

## [Enumerations and Structures](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html#:~:text=sideLength%20%3D%20optionalSquare%3F.sideLength-,Enumerations%20and%20Structures,-Use%20enum%20to)

Use `enum` to create an enumeration. Like classes and all other named types, enumerations can have methods associated with them.

```swift
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

> EXPERIMENT
>
> Write a function that compares two `Rank` values by comparing their raw values.

By default, Swift assigns the raw values starting at zero and incrementing by one each time, but you can change this behavior by explicitly specifying values. In the example above, `Ace` is explicitly given a raw value of `1`, and the rest of the raw values are assigned in order. You can also use strings or floating-point numbers as the raw type of an enumeration. Use the `rawValue` property to access the raw value of an enumeration case.

Use the `init?(rawValue:)` initializer to make an instance of an enumeration from a raw value. It returns either the enumeration case matching the raw value or `nil` if there’s no matching `Rank`.

```swift
if let convertedRank = Rank(rawValue: 3) {
    let threeDescription = convertedRank.simpleDescription()
}
```

The case values of an enumeration are actual values, not just another way of writing their raw values. In fact, in cases where there isn’t a meaningful raw value, you don’t have to provide one.

```swift
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

> EXPERIMENT
>
> Add a `color()` method to `Suit` that returns “black” for spades and clubs, and returns “red” for hearts and diamonds.

Notice the two ways that the `hearts` case of the enumeration is referred to above: When assigning a value to the `hearts` constant, the enumeration case `Suit.hearts` is referred to by its full name because the constant doesn’t have an explicit type specified. Inside the switch, the enumeration case is referred to by the abbreviated form `.hearts` because the value of `self` is already known to be a suit. You can use the abbreviated form anytime the value’s type is already known.

If an enumeration has raw values, those values are determined as part of the declaration, which means every instance of a particular enumeration case always has the same raw value. Another choice for enumeration cases is to have values associated with the case—these values are determined when you make the instance, and they can be different for each instance of an enumeration case. You can think of the associated values as behaving like stored properties of the enumeration case instance. For example, consider the case of requesting the sunrise and sunset times from a server. The server either responds with the requested information, or it responds with a description of what went wrong.

```swift
enum ServerResponse {
    case result(String, String)
    case failure(String)
}

let success = ServerResponse.result("6:00 am", "8:09 pm")
let failure = ServerResponse.failure("Out of cheese.")

switch success {
case let .result(sunrise, sunset)
    print("Sunrise is at \(sunrise) and sunset is at \(sunset).")
case let .failure(message):
    print("Failure...  \(message)")
}
// Prints "Sunrise is at 6:00 am and sunset is at 8:09 pm."
```

> EXPERIMENT
>
> Add a third case to `ServerResponse` and to the switch.

Notice how the sunrise and sunset times are extracted from the `ServerResponse` value as part of matching the value against the switch cases.

Use `struct` to create a structure. Structures support many of the same behaviors as classes, including methods and initializers. One of the most important differences between structures and classes is that structures are always copied when they’re passed around in your code, but classes are passed by reference.

```swift
struct Card {
    var rank: Rank
    var suit: Suit
    func simpleDescription() -> String {
        return "The \(rank.simpleDescription()) of \(suit.simpleDescription())"
    }
}
let threeOfSpades = Card(rank: .three, suit: .spades)
let threeOfSpadesDescription = threeOfSpades.simpleDescription()
```

> EXPERIMENT
>
> Write a function that returns an array containing a full deck of cards, with one card of each combination of rank and suit.

---

## 열거형과 구조체

`enum` 을 사용하여 열거형을 만듭니다. 클래스와 다른 모든 명명된 타입들처럼 열거형도 관련된 메소드를 가질 수 있습니다. 

```swift
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
> 두 개의 `Rank` 값을 그들의 원시값으로 비교하는 함수를 작성하십시오.

기본적으로, 스위프트는 0 부터 시작해서 1씩 증가하는 원시값을 할당하지만, 명시적으로 값을 지정해서 그 동작을 변경할 수 있습니다. 위의 예에서 `Ace` 는 명시적으로 1의 값이 주어졌고, 나머지 원시값들은 순서에 따라 할당됩니다. 또한 문자열이나 부동 소수점 숫자도 열거형의 원시 타입으로 사용할 수 있습니다. `rawValue` 속성을 사용하여 열거형 케이스의 원시값에 접근합니다. 

`init?(rawValue:)` 생성자를 사용하여 원시값으로부터 열거형의 인스턴스를 만듭니다. 원시값과 일치하는 열거형 케이스를 반환하거나 만약 일치하는 `Rank` 가 없다면 `nil` 을 반환합니다. 

```swift
if let convertedRank = Rank(rawValue: 3) {
    let threeDescription = convertedRank.simpleDescription()
}
```

열거형의 케이스 값은 그들의 원시값을 작성하는 또 다른 방법이 아니라 실제 값입니다. 사실, 의미있는 원시값이 없다면 꼭 제공할 필요는 없습니다. 

```swift
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
> `Suit` 에 스페이드와 클럽에는 "검정"을 반환하고, 하트와 다이아몬드에는 "빨강"을 반환하는 `color()` 메소드를 추가하십시오.

위에서 열거형의 `hearts` 케이스를 참조하는 두 가지 방법에 주목하십시오: `hearts` 상수에 값을 할당할 때, 이 상수에 명시적인 타입이 지정되어 있지 않기 때문에, 열거형 케이스 `Suit.hearts` 는 풀네임으로 참조됩니다. 스위치문 내부에서 `self` 의 값은 이미 suit 라고 알려져 있기 때문에, 열거형 케이스는 축약된 `.hearts` 형태로 참조됩니다. 값의 타입을 이미 알고 있다면 언제나 축약된 형태를 사용할 수 있습니다. 

열거형이 원시값을 가지고 있다면, 그 값들은 선언의 일부로써 결정됩니다. 그 말은 특정한 열거형 케이스의 모든 인스턴스들이 같은 원시값을 가진다는 의미입니다. 열거형 케이스에 대한 또 다른 선택은 그 케이스와 관련된 값을 가지는 것입니다. 이 값들은 인스턴스를 생성할 때 결정되고 열거형 케이스의 인스턴스 마다 다를 수 있습니다. 관련된 값들은 열거형 케이스 인스턴스의 저장 프로퍼티 같은 행동으로 생각할 수 있습니다. 예를 들어, 서버에 일출과 일몰 시간을 요청하는 경우를 생각해보십시오. 서버는 요청된 정보와 함께 응답하거나, 무엇이 잘못 되었는지에 대한 설명과 함께 응답합니다. 

```swift
enum ServerResponse {
    case result(String, String)
    case failure(String)
}

let success = ServerResponse.result("6:00 am", "8:09 pm")
let failure = ServerResponse.failure("Out of cheese.")

switch success {
case let .result(sunrise, sunset)
    print("Sunrise is at \(sunrise) and sunset is at \(sunset).")
case let .failure(message):
    print("Failure...  \(message)")
}
// "Sunrise is at 6:00 am and sunset is at 8:09 pm." 출력
```

> 실험
>
> 세 번째 케이스를 `ServerResponse` 와 스위치문에 추가하십시오.

스위치 케이스에 대하여 일치하는 값의 일부분으로써,  `ServerResponse` 값으로부터 일출과 일몰 시간이 어떻게 추출되는지에 주목하십시오.

`struct` 를 사용하여 구조체를 만듭니다. 구조체는 메소드와 생성자를 포함하여 클래스와 동일한 행동을 많이 지원합니다. 구조체와 클래스의 가장 중요한 차이점 중 하나는 코드 안에서 주변으로 전달될 때, 구조체는 항상 복사되고 클래스는 참조로 전달된다는 것입니다. 

```swift
struct Card {
    var rank: Rank
    var suit: Suit
    func simpleDescription() -> String {
        return "The \(rank.simpleDescription()) of \(suit.simpleDescription())"
    }
}
let threeOfSpades = Card(rank: .three, suit: .spades)
let threeOfSpadesDescription = threeOfSpades.simpleDescription()
```

> 실험
>
> 각각의 카드가 rank와 suit의 조합인 카드의 전체 덱을 포함하는 배열을 반환하는 함수를 작성하십시오.

---

_* enumeration : 열거_</br>
_* abbreviated : 축약된_</br>

---

</details>
