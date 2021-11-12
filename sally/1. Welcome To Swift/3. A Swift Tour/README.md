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

