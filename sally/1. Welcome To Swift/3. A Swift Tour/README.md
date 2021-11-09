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

Values are never implicitly converted to another type. If you need to convert a value to a different type, explicitly make an instance of the desired type.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

> EXPERIMENT
>
> Try removing the conversion to `String` from the last line. What error do you get?

```swift
error: binary operator '+' cannot be applied to operands of type 'String' and 'Int'
```

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

값은 결코 암묵적으로 다른 타입으로 변환되지 않습니다. 만약 값을 다른 타입으로 변환해야 한다면, 요구되는 타입의 인스턴스를 명시적으로 만드십시오.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

> 실험
>
> 마지막 줄에서 `String` 으로 변환하는 것을 제거해 보십시오. 어떤 오류가 발생합니까?

```swift
오류: 이항 연산자 '+'는 'String'과 'Int' 타입의 피연산자에 적용할 수 없습니다.
```

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

