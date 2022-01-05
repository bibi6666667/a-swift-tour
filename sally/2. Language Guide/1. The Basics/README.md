# The Basics

<details>
	<summary>Outline</summary>

## [Outline](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=ON%20THIS%20PAGE-,The%20Basics,-Swift%20is%20a)

Swift is a new programming language for iOS, macOS, watchOS, and tvOS app development. Nonetheless, many parts of Swift will be familiar from your experience of developing in C and Objective-C.

Swift provides its own versions of all fundamental C and Objective-C types, including `Int` for integers, `Double` and `Float` for floating-point values, `Bool` for Boolean values, and `String` for textual data. Swift also provides powerful versions of the three primary collection types, `Array`, `Set`, and `Dictionary`, as described in [Collection Types](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html).

Like C, Swift uses variables to store and refer to values by an identifying name. Swift also makes extensive use of variables whose values can’t be changed. These are known as constants, and are much more powerful than constants in C. Constants are used throughout Swift to make code safer and clearer in intent when you work with values that don’t need to change.

In addition to familiar types, Swift introduces advanced types not found in Objective-C, such as tuples. Tuples enable you to create and pass around groupings of values. You can use a tuple to return multiple values from a function as a single compound value.

Swift also introduces optional types, which handle the absence of a value. Optionals say either “there *is* a value, and it equals *x*” or “there *isn’t* a value at all”. Using optionals is similar to using `nil` with pointers in Objective-C, but they work for any type, not just classes. Not only are optionals safer and more expressive than `nil` pointers in Objective-C, they’re at the heart of many of Swift’s most powerful features.

Swift is a *type-safe* language, which means the language helps you to be clear about the types of values your code can work with. If part of your code requires a `String`, type safety prevents you from passing it an `Int` by mistake. Likewise, type safety prevents you from accidentally passing an optional `String` to a piece of code that requires a non-optional `String`. Type safety helps you catch and fix errors as early as possible in the development process.

---

## 개요

스위프트는 iOS, macOS, watchOS, tvOS 앱 개발을 위한 새로운 프로그래밍 언어입니다. 그럼에도 불구하고, C 와 Objective-C 에서의 개발 경험을 통해, 스위프트의 많은 부분들을 친숙하게 느낄 수 있습니다.

스위프트는 정수를 위한 `Int`, 부동 소수점 값을 위한 `Double` 과 `Float`, 참거짓 값을 위한 `Bool`, 문자열 데이터를 위한 `String` 를 포함하여, C 와 Objective-C 타입의 모든 근본적인 그 자체 버전을 제공합니다. 또한 [Collection Types](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html)에서 설명하는 세 가지의 기본 컬렉션 타입 `Array`, `Set`, 및 `Dictionary` 의 강력한 버전을 제공합니다. 

C 처럼, 스위프트는 구별되는 이름으로 변수를 사용하여 값을 저장하거나 참조합니다. 또한 변경 불가능한 값을 가지는 변수를 광범위하게 사용합니다. 이것은 상수이고, C 에서보다 강력합니다. 스위프트에서 변경할 필요가 없는 값으로 작업할 때 상수를 사용하여 의도적으로 코드를 더 안전하고 명확하게 만들 수 있습니다. 

스위프트는 친숙한 타입들 외에도, Objective-C 에서는 없던 개선된 타입인 튜플 같은 것들을 도입했습니다. 튜플을 사용하여 값의 그룹을 만들고 주변으로 전달할 수 있습니다. 튜플을 사용하여 함수로부터 여러 개의 값을 단일 값 복합체 처럼 반환할 수 있습니다. 

또한 스위프트는 값의 부재를 다루는 옵셔널 타입을 도입했습니다. 옵셔널은 "값이 *있고*, *x* 와 동일하다" 혹은 "값이 전혀 *없다*" 중 하나를 말해줍니다. 옵셔널의 사용을 사용하는 것은 Objective-C 에서 포인터와 함께 `nil` 을 사용하는 것과 비슷하지만, 클래스에서만 작동하는 것이 아니라 모든 타입에서 작동합니다. 옵셔널은 Objective-C 에서의 `nil` 포인터보다 더 안전하고 표현력이 좋을 뿐만 아니라, 스위프트의 많은 가장 강력한 기능들의 심장입니다. 

스위프트는 *type-safe* 언어입니다. 즉, 언어가 코드에서 사용할 수 있는 값의 타입이 더 명확해지도록 도와준다는 의미입니다. 코드 중에 `String` 을 요구하는 부분이 있다면, 타입 안정성은 실수로 `Int` 를 넘겨주는 것을 방지해 줄 것입니다. 마찬가지로, 타입 안정성은 옵셔널이 아닌 `String` 을 요구하는 코드 조각에 실수로 옵셔널 `String` 을 전달하는 것도 방지해 줄 것입니다. 타입 안정성은 개발 과정에서 가능한 한 빨리 오류를 찾아내고 고칠 수 있도록 도와줍니다. 

---

_* nonetheless : 그럼에도 불구하고_</br>
_* extensive : 광범위한_</br>
_* in intent : 의도적으로_</br>
_* absence : 부재_</br>
_* at all : 조금도, 조금도 ~아니다_</br>
_* expressive : 표현이 풍부한, 나타내는_</br>

---

</details>

<details>
	<summary>Constants and Variables</summary>

## [Constants and Variables](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=ON%20THIS%20PAGE-,The%20Basics,-Swift%20is%20a)

Constants and variables associate a name (such as `maximumNumberOfLoginAttempts` or `welcomeMessage`) with a value of a particular type (such as the number `10` or the string `"Hello"`). The value of a *constant* can’t be changed once it’s set, whereas a *variable* can be set to a different value in the future.

### Declaring Constants and Variables

Constants and variables must be declared before they’re used. You declare constants with the `let` keyword and variables with the `var` keyword. Here’s an example of how constants and variables can be used to track the number of login attempts a user has made:

```swift
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
```

This code can be read as:

“Declare a new constant called `maximumNumberOfLoginAttempts`, and give it a value of `10`. Then, declare a new variable called `currentLoginAttempt`, and give it an initial value of `0`.”

In this example, the maximum number of allowed login attempts is declared as a constant, because the maximum value never changes. The current login attempt counter is declared as a variable, because this value must be incremented after each failed login attempt.

You can declare multiple constants or multiple variables on a single line, separated by commas:

```swift
var x = 0.0, y = 0.0, z = 0.0
```

> NOTE
>
> If a stored value in your code won’t change, always declare it as a constant with the `let` keyword. Use variables only for storing values that need to be able to change.

### Type Annotations

You can provide a *type annotation* when you declare a constant or variable, to be clear about the kind of values the constant or variable can store. Write a type annotation by placing a colon after the constant or variable name, followed by a space, followed by the name of the type to use.

This example provides a type annotation for a variable called `welcomeMessage`, to indicate that the variable can store `String` values:

```swift
var welcomeMessage: String
```

The colon in the declaration means “…of type…,” so the code above can be read as:

“Declare a variable called `welcomeMessage` that’s of type `String`.”

The phrase “of type `String`” means “can store any `String` value.” Think of it as meaning “the type of thing” (or “the kind of thing”) that can be stored.

The `welcomeMessage` variable can now be set to any string value without error:

```swift
welcomeMessage = "Hello"
```

You can define multiple related variables of the same type on a single line, separated by commas, with a single type annotation after the final variable name:

```swift
var red, green, blue: Double
```

> NOTE
>
> It’s rare that you need to write type annotations in practice. If you provide an initial value for a constant or variable at the point that it’s defined, Swift can almost always infer the type to be used for that constant or variable, as described in [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322). In the `welcomeMessage` example above, no initial value is provided, and so the type of the `welcomeMessage` variable is specified with a type annotation rather than being inferred from an initial value.

### Naming Constants and Variables

Constant and variable names can contain almost any character, including Unicode characters:

```swift
let π = 3.14159
let 你好 = "你好世界"
let 🐶🐮 = "dogcow"
```

Constant and variable names can’t contain whitespace characters, mathematical symbols, arrows, private-use Unicode scalar values, or line- and box-drawing characters. Nor can they begin with a number, although numbers may be included elsewhere within the name.

Once you’ve declared a constant or variable of a certain type, you can’t declare it again with the same name, or change it to store values of a different type. Nor can you change a constant into a variable or a variable into a constant.

> NOTE
>
> If you need to give a constant or variable the same name as a reserved Swift keyword, surround the keyword with backticks (\`) when using it as a name. However, avoid using keywords as names unless you have absolutely no choice.

You can change the value of an existing variable to another value of a compatible type. In this example, the value of `friendlyWelcome` is changed from `"Hello!"` to `"Bonjour!"`:

```swift
var friendlyWelcome = "Hello!"
friendlyWelcome = "Bonjour!"
// friendlyWelcome is now "Bonjour!"
```

Unlike a variable, the value of a constant can’t be changed after it’s set. Attempting to do so is reported as an error when your code is compiled:

```swift
let languageName = "Swift"
languageName = "Swift++"
// This is a compile-time error: languageName cannot be changed.
```

### Printing Constants and Variables

You can print the current value of a constant or variable with the `print(_:separator:terminator:)` function:

```swift
print(friendlyWelcome)
// Prints "Bonjour!"
```

The `print(_:separator:terminator:)` function is a global function that prints one or more values to an appropriate output. In Xcode, for example, the `print(_:separator:terminator:)` function prints its output in Xcode’s “console” pane. The `separator` and `terminator` parameter have default values, so you can omit them when you call this function. By default, the function terminates the line it prints by adding a line break. To print a value without a line break after it, pass an empty string as the terminator—for example, `print(someValue, terminator: "")`. For information about parameters with default values, see [Default Parameter Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID169).

Swift uses *string interpolation* to include the name of a constant or variable as a placeholder in a longer string, and to prompt Swift to replace it with the current value of that constant or variable. Wrap the name in parentheses and escape it with a backslash before the opening parenthesis:

```swift
print("The current value of friendlyWelcome is \(friendlyWelcome)")
// Prints "The current value of friendlyWelcome is Bonjour!"
```

> NOTE
>
> All options you can use with string interpolation are described in [String Interpolation](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html#ID292).

---

## 상수와 변수

상수와 변수는 이름(예: `maximumNumberOfLoginAttempts` 혹은 `welcomeMessage`)과 특정한 타입의 값(예: 숫자 `10` 이나 문자열 `"Hello"`) 을 서로 연관 지어줍니다. *상수*의 값은 한번 할당하면 변경할 수 없지만, *변수*의 값은 나중에 다른 값을 할당할 수 있습니다. 

### 상수와 변수의 선언

상수와 변수는 반드시 사용되기 전에 선언되어야 합니다. 상수는 `let` 키워드로 선언하고, 변수는 `var` 키워드로 선언합니다. 여기에 유저가 로그인을 시도하는 횟수를 추적하기 위해 상수와 변수를 어떻게 사용할 수 있는지에 대한 예가 있습니다:

```swift
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
```

이 코드는 이런 식으로 해석할 수 있습니다:

"`maximumNumberOfLoginAttempts` 라는 새로운 상수를 선언하고, `10` 을 할당합니다. 그리고, `currentLoginAttempt` 라는 새로운 변수를 선언하고, 초기값으로  `0` 을 할당합니다. "

이 예에서, 최대값은 절대 변경되지 않기 때문에, 가능한 로그인 시도 횟수의 최대값은 상수로 선언되었습니다. 현재 로그인 시도 횟수는 로그인 시도가 실패할 때마다 증가해야 하기 때문에 변수로 선언되었습니다. 

여러 개의 변수를 콤마로 구분하여 한 줄에서 선언할 수 있습니다:

```swift
var x = 0.0, y = 0.0, z = 0.0
```

> 노트
>
> 코드에 있는 저장 변수가 변하지 않는다면, 언제나 `let` 키워드를 사용하여 상수로 선언하십시오. 변할 필요가 있는 있는 저장 변수에만 변수를 사용하십시오. 

### 타입 주석

상수나 변수를 선언할 때, *type annotation* 를 사용하여 그것들에 저장할 수 있는 종류의 값들을 명확하게 할 수 있습니다. 타입 주석을 작성하려면 상수나 변수 이름 뒤에 콜론을 적고, 한칸 띄우고 사용하려는 타입의 이름을 적으십시오. 

이 예에서 타입 주석은 `welcomeMessage` 라는 이름의 변수가 `String` 값을 저장할 수 있다는 것을 알려줍니다:

```swift
var welcomeMessage: String
```

저 선언에서 콜론은 "...타입의...," 라는 의미이기 때문에, 위의 코드는 이렇게 읽을 수 있습니다: 

"`String` 타입의 `welcomeMessage` 이라는 이름의 변수 선언."

"`String` 타입의” 라는 구절은 "어떠한 `String` 값이든 저장 가능" 이라는 뜻입니다. 저장할 수 있는 "어떤 것의 타입" (혹은 "어떤 것의 종류") 라는 의미라고 생각하십시오.

이제 `welcomeMessage` 변수는 어떤 문자열 값이든 오류 없이 설정할 수 있습니다:

```swift
welcomeMessage = "Hello"
```

여러 개의 연관된 같은 타입 변수들을 한 줄에서 정의하려면, 콤마로 구분하고 마지막 변수 이름 뒤에 하나의 타입 주석을 사용하십시오: 

```swift
var red, green, blue: Double
```

> 노트
>
> 실제로 타입 주석을 작성해야할 필요가 있는 경우는 적습니다. 상수나 변수를 처음 정의할 때 초기값을 제공하면, [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322) 에서 설명하는 것 처럼, 스위프트가 거의 항상 그 타입을 추론할 수 있습니다. 위의 `welcomeMessage` 예에서는 초기값이 주어지지 않았기 때문에, `welcomeMessage` 변수의 타입은 초기값으로부터 추론하지 않고 타입 주석으로 정해집니다. 

### 상수와 변수의 작명

상수와 변수의 이름은 유니코드 문자를 포함하여 거의 모든 문자를 포함시킬 수 있습니다: 

```swift
let π = 3.14159
let 你好 = "你好世界"
let 🐶🐮 = "dogcow"
```

공백 문자, 수학 기호, 화살표, 개인용 유니코드 스칼라 값, 혹은 선 그리기 문자와 박스 그리기 문자는 상수와 변수의 이름에 포함될 수 없습니다. 또, 숫자로 이름을 시작하는 것은 불가능 하지만, 다른 곳에는 숫자를 포함시킬 수 있습니다.

상수나 변수를 한번 특정한 타입으로 선언하면, 같은 이름으로 다시 선언하거나 다른 타입의 값을 저장하도록 변경하는 것은 불가능합니다. 상수를 변수로 변경하거나 변수를 상수로 변경하는 것도 불가능합니다. 

> 노트
>
> 백틱(\`)으로 키워드를 감싸면 상수나 변수에 스위프트의 예약어와 같은 이름을 줄 수 있습니다. 하지만, 다른 선택지가 전혀 없을 때를 제외하고는 예약어를 이름으로 사용하는 것은 피하십시오. 

기존 변수의 값을 호환 가능한 타입의 다른 값으로 변경할 수 있습니다. 예를 들어, `friendlyWelcome` 의 값은  `"Hello!"` 에서 `"Bonjour!"` 으로 변경 되었습니다:

```swift
var friendlyWelcome = "Hello!"
friendlyWelcome = "Bonjour!"
// friendlyWelcome 은 이제 "Bonjour!" 입니다. 
```

변수와 달리, 상수의 값은 한번 설정된 후에는 변경할 수 없습니다. 그런 시도는 코드가 컴파일 될 때 오류로 보고 됩니다:

```swift
let languageName = "Swift"
languageName = "Swift++"
// 컴파일 타임 에러: languageName은 변경이 불가능 합니다. 
```

### 상수와 변수의 출력

 `print(_:separator:terminator:)` 함수를 사용하여 상수나 변수의 현재 값을 출력할 수 있습니다: 

```swift
print(friendlyWelcome)
// "Bonjour!" 출력
```

`print(_:separator:terminator:)`  함수는 하나 혹은 더 많은 값들을 적절한 결과값으로 출력하는 전역 함수입니다. Xcode에서, 예를 들어,  `print(_:separator:terminator:)` 함수는 Xcode의 "콘솔" 창에 결과값을 출력합니다. `separator` 와 `terminator` 매개변수는 기본값을 가지기 때문에, 이 함수를 호출할 때 생략할 수 있습니다. 기본적으로, 함수는 줄바꿈을 추가하여 출력하는 줄을 종료합니다. 뒤에 줄바꿈 없이 값을 출력하려면 `print(someValue, terminator: "")` 처럼 종료 매개변수로 빈 문자열을 넘겨주십시오. 기본값을 비롯하여 매개변수에 대한 정보는 [Default Parameter Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID169) 에서 볼 수 있습니다. 

스위프트는 문자열 보간을 사용하여 더 긴 문자열에 상수나 변수의 이름을 자리 표시자로 포함시킬 수 있고, 그 상수나 변수의 현재값으로 대체하도록 할 수 있습니다. 괄호로 이름을 감싸고, 여는 괄호 앞에 백슬래시를 넣어서 탈출합니다:

```swift
print("The current value of friendlyWelcome is \(friendlyWelcome)")
// "The current value of friendlyWelcome is Bonjour!" 출력
```

> 노트
>
> 문자열 보간과 함께 사용할 수 있는 모든 옵션은 [String Interpolation](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html#ID292) 에서 설명되어 있습니다. 

---

_* annotation : 주석_</br>
_* mathematical symbol : 수학 기호_</br>
_* private-use : 개인용_</br>
_* appropriate : 적절한_</br>
_* pane : 창, 창유리_</br>
_* terminate : 종료, 끝내다_</br>
_* line break : 줄 바꿈_</br>
_* interpolation : 보간, 삽입_</br>
_* placeholder : 자리 표시자_</br>
_* prompt : 자극하다, 즉각적인_</br>

---

</details>

<details>
	<summary>Comments</summary>

## [Comments](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=in%20String%20Interpolation.-,Comments,-Use%20comments%20to)

Use comments to include nonexecutable text in your code, as a note or reminder to yourself. Comments are ignored by the Swift compiler when your code is compiled.

Comments in Swift are very similar to comments in C. Single-line comments begin with two forward-slashes (`//`):

```swift
// This is a comment.
```

Multiline comments start with a forward-slash followed by an asterisk (`/*`) and end with an asterisk followed by a forward-slash (`*/`):

```swift
/* This is also a comment
but is written over multiple lines. */
```

Unlike multiline comments in C, multiline comments in Swift can be nested inside other multiline comments. You write nested comments by starting a multiline comment block and then starting a second multiline comment within the first block. The second block is then closed, followed by the first block:

```swift
/* This is the start of the first multiline comment.
 /* This is the second, nested multiline comment. */
This is the end of the first multiline comment. */
```

Nested multiline comments enable you to comment out large blocks of code quickly and easily, even if the code already contains multiline comments.

---

## 주석

노트로 사용하거나 스스로 리마인드 하기 위해 코드에서 실행하지 않는 텍스트를 주석처리 하십시오. 코드가 컴파일 될 때 스위프트 컴파일러는 주석을 무시합니다. 

스위프트에서 주석은 C의 주석과 비슷합니다. 한 줄 짜리 주석은 두개의 슬래시 (`//`) 로 시작합니다: 

```swift
// 주석입니다. 
```

여러 줄의 주석은 슬래시와 별표 (`/*`) 로 시작하고, 별표와 슬래시 (`*/`) 로 끝납니다: 

```swift
/* 이것도 주석이지만
여러 줄에 걸쳐 작성 되었습니다. */
```

C의 여러 줄 주석과 달리 스위프트에서는 주석 안에 다른 여러 줄 주석을 중첩시킬 수 있습니다. 중첩된 주석을 작성하기 위해서는 첫 번째 여러 줄 주석 블럭으로 시작하고, 그 안에서 두 번째 여러 줄 주석을 시작합니다. 그 후에 두 번째 블럭이 닫히고, 첫 번째 블럭이 닫힙니다:

```swift
/* 첫 번째 여러 줄 주석의 시작입니다. 
 /* 두 번째인 중첩된 여러 줄 주석입니다. */
첫 번째 여러 줄 주석의 끝입니다. */
```

여러 줄 주석 중첩은 이미 여러 줄 주석을 포함하고 있어도 많은 양의 코드를 빠르고 쉽게 주석처리 할 수 있게 해줍니다. 

---

_* asterisk : 별표_</br>

---

</details>

<details>
	<summary>Semicolons</summary>

## [Semicolons](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=contains%20multiline%20comments.-,Semicolons,-Unlike%20many%20other)

Unlike many other languages, Swift doesn’t require you to write a semicolon (`;`) after each statement in your code, although you can do so if you wish. However, semicolons *are* required if you want to write multiple separate statements on a single line:

```swift
let cat = "🐱"; print(cat)
// Prints "🐱"
```

---

## 세미콜론

다른 여러 언어와 달리 스위프트는, 원한다면 가능하긴 하지만, 코드의 각 문장 뒤에 세미콜론을 작성할 필요가 없습니다. 그러나 한 줄에 여러 개의 분리된 문장을 작성하려면 세미콜론이 필요합니다:

```swift
let cat = "🐱"; print(cat)
// "🐱" 출력
```

---

</details>

<details>
	<summary>Integers</summary>

## [Integers](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=//%20Prints%20%22%F0%9F%90%B1%22-,Integers,-Integers%20are%20whole)

*Integers* are whole numbers with no fractional component, such as `42` and `-23`. Integers are either *signed* (positive, zero, or negative) or *unsigned* (positive or zero).

Swift provides signed and unsigned integers in 8, 16, 32, and 64 bit forms. These integers follow a naming convention similar to C, in that an 8-bit unsigned integer is of type `UInt8`, and a 32-bit signed integer is of type `Int32`. Like all types in Swift, these integer types have capitalized names.

### Integer Bounds

You can access the minimum and maximum values of each integer type with its `min` and `max` properties:

```swift
let minValue = UInt8.min  // minValue is equal to 0, and is of type UInt8
let maxValue = UInt8.max  // maxValue is equal to 255, and is of type UInt8
```

The values of these properties are of the appropriate-sized number type (such as `UInt8` in the example above) and can therefore be used in expressions alongside other values of the same type.

### Int

In most cases, you don’t need to pick a specific size of integer to use in your code. Swift provides an additional integer type, `Int`, which has the same size as the current platform’s native word size:

- On a 32-bit platform, `Int` is the same size as `Int32`.
- On a 64-bit platform, `Int` is the same size as `Int64`.

Unless you need to work with a specific size of integer, always use `Int` for integer values in your code. This aids code consistency and interoperability. Even on 32-bit platforms, `Int` can store any value between `-2,147,483,648` and `2,147,483,647`, and is large enough for many integer ranges.

### UInt

Swift also provides an unsigned integer type, `UInt`, which has the same size as the current platform’s native word size:

- On a 32-bit platform, `UInt` is the same size as `UInt32`.
- On a 64-bit platform, `UInt` is the same size as `UInt64`.

> NOTE
>
> Use `UInt` only when you specifically need an unsigned integer type with the same size as the platform’s native word size. If this isn’t the case, `Int` is preferred, even when the values to be stored are known to be nonnegative. A consistent use of `Int` for integer values aids code interoperability, avoids the need to convert between different number types, and matches integer type inference, as described in [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322).

---

## 정수

*정수*는 42나 -23 처럼 분수 요소가 없는 통째의 숫자입니다. 정수는 *부호가 있거나* (양수, 0, 혹은 음수) *부호가 없습니다* (양수 혹은 0).

스위프트는 부호가 있는 정수와 부호가 없는 정수를 8, 16, 32, 64 비트 형식으로 제공합니다. 이러한 정수들은 C 와 비슷한 네이밍 컨벤션을 따릅니다. 8 비트의 부호가 없는 정수의 타입은 `UInt8`, 32 비트의 부호가 있는 정수의 타입은 `Int32` 입니다. 스위프트의 모든 타입들 처럼, 이 정수 타입들의 이름은 대문자로 시작합니다. 

### 정수 범위

`min` 과 `max` 프로퍼티를 이용하여 각 정수의 최소값과 최대값에 접근할 수 있습니다:  

```swift
let minValue = UInt8.min  // minValue는 0이고, UInt8 타입입니다
let maxValue = UInt8.max  // maxValue는 255이고, UInt8 타입입니다.
```

이러한 프로퍼티들의 값은 (위의 예의 `UInt8` 같은) 적절한 사이즈의 숫자 타입이므로, 표현식에서 같은 타입의 다른 값들과 나란히 사용될 수 있습니다. 

### Int

대부분의 경우, 코드에서 사용하기 위해 특정한 크기의 정수를 고를 필요는 없습니다. 스위프트는 현재 플랫폼의 기본 단어 크기와 같은 크기를 가지는 `Int` 라는 추가적인 정수 타입을 제공합니다:

- 32-비트 플랫폼에서, `Int` 는 `Int32` 와 같은 크기를 가집니다.

- 64-비트 플랫폼에서, `Int` 는 `Int64` 와 같은 크기를 가집니다.

특정한 크기의 정수를 사용해야하는 경우를 제외하고는 코드에서 정수 값을 사용할 때 `Int` 를 사용하십시오. 이것이 코드가 일관적이고 상호 운용적이도록 도와줍니다. 32-비트 플랫폼에서도 `Int` 는 `-2,147,483,648` 와 `2,147,483,647` 사이의 어떤 값이라도 저장할 수 있고, 이것은 많은 정수 범위를 충분히 만족시킬 수 있습니다.

### UInt

또한 스위프트는 현재 플랫폼의 기본 단어 크기와 같은 크기를 가지는 `UInt` 라는 부호가 없는 정수 타입을 제공합니다:

- 32-비트 플랫폼에서, `UInt` 는 `UInt32` 와 같은 크기를 가집니다.
- 64-비트 플랫폼에서, `UInt` 는 `UInt64` 와 같은 크기를 가집니다.

> 노트
>
> `UInt` 는 플랫폼의 기본 단어 크기와 같은 부호가 없는 정수 타입이 특별하게 필요할 때만 사용하십시오. 그렇지 않은 경우, 변수에 저장될 값이 음수가 아니라고 알려져 있더라도 `Int` 를 사용하는 것을 권장합니다. 정수 값으로 `Int` 를 일관되게 사용하는 것은 코드가 상호 운용적이게 도와주고, 다른 숫자 타입 사이에서 변환할 필요가 없게 해주고, [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322) 에서 묘사된 것처럼 정수 타입 추론을 맞춰줍니다.

---

_* fractional : 분수_</br>
_* *sign* : 부호_</br>
_* capitalized : 대문자, 대문자로 시작하다_</br>
_* alongside : 나란히_</br>
_* consistency : 일관성_</br>
_* interoperability : 상호 운용성_</br>
_* If this isn’t the case : 그렇지 않은 경우_</br>

---

</details>

<details>
	<summary>Floating-Point Numbers</summary>

## [Floating-Point Numbers](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=and%20Type%20Inference.-,Floating-Point%20Numbers,-Floating-point%20numbers)

*Floating-point numbers* are numbers with a fractional component, such as `3.14159`, `0.1`, and `-273.15`.

Floating-point types can represent a much wider range of values than integer types, and can store numbers that are much larger or smaller than can be stored in an `Int`. Swift provides two signed floating-point number types:

- `Double` represents a 64-bit floating-point number.
- `Float` represents a 32-bit floating-point number.

> NOTE
>
> `Double` has a precision of at least 15 decimal digits, whereas the precision of `Float` can be as little as 6 decimal digits. The appropriate floating-point type to use depends on the nature and range of values you need to work with in your code. In situations where either type would be appropriate, `Double` is preferred.

---

## 부동 소수점 숫자

*부동 소수점 숫자*는  `3.14159`, `0.1`, 나 `-273.15` 등과 같이 분수 요소가 있는 숫자입니다. 

부동 소수점 타입은 정수 타입 보다 더 넓은 범위의 값을 표현할 수 있고, `Int`에 저장할 수 있는 숫자보다 더 크거나 작은 숫자를 저장할 수 있습니다. 스위프트는 두 가지 부호가 있는 부동 소수점 숫자 타입을 제공합니다:

- 64-비트 부동 소수점 숫자를 표현하는 `Double`.
- 32-비트 부동 소수점 숫자를 표현하는 `Float`.

> 노트
>
> `Double`의 정밀도는 최소 15자리 소수점 이하 자릿수인 반면, `Float`의 정밀도는 소수점 이하 6자리까지 가능합니다. 적절한 부동 소수점 타입을 사용하는 것은 코드에서 사용해야 하는 값의 특성과 범위에 달려있습니다. 두 타입 모두 적절한 경우에는 `Double`이 선호됩니다. 

---

_* nature : 특성_</br>

---

</details>

<details>
	<summary>Type Safety and Type Inference</summary>

## [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=Double%20is%20preferred.-,Type%20Safety%20and%20Type%20Inference,-Swift%20is%20a)

Swift is a *type-safe* language. A type safe language encourages you to be clear about the types of values your code can work with. If part of your code requires a `String`, you can’t pass it an `Int` by mistake.

Because Swift is type safe, it performs *type checks* when compiling your code and flags any mismatched types as errors. This enables you to catch and fix errors as early as possible in the development process.

Type-checking helps you avoid errors when you’re working with different types of values. However, this doesn’t mean that you have to specify the type of every constant and variable that you declare. If you don’t specify the type of value you need, Swift uses *type inference* to work out the appropriate type. Type inference enables a compiler to deduce the type of a particular expression automatically when it compiles your code, simply by examining the values you provide.

Because of type inference, Swift requires far fewer type declarations than languages such as C or Objective-C. Constants and variables are still explicitly typed, but much of the work of specifying their type is done for you.

Type inference is particularly useful when you declare a constant or variable with an initial value. This is often done by assigning a *literal value* (or *literal*) to the constant or variable at the point that you declare it. (A literal value is a value that appears directly in your source code, such as `42` and `3.14159` in the examples below.)

For example, if you assign a literal value of `42` to a new constant without saying what type it is, Swift infers that you want the constant to be an `Int`, because you have initialized it with a number that looks like an integer:

```swift
let meaningOfLife = 42
// meaningOfLife is inferred to be of type Int
```

Likewise, if you don’t specify a type for a floating-point literal, Swift infers that you want to create a `Double`:

```swift
let pi = 3.14159
// pi is inferred to be of type Double
```

Swift always chooses `Double` (rather than `Float`) when inferring the type of floating-point numbers.

If you combine integer and floating-point literals in an expression, a type of `Double` will be inferred from the context:

```swift
let anotherPi = 3 + 0.14159
// anotherPi is also inferred to be of type Double
```

The literal value of `3` has no explicit type in and of itself, and so an appropriate output type of `Double` is inferred from the presence of a floating-point literal as part of the addition.

---

## 타입 안정성과 타입 추론

스위프트는 *type-safe* 언어입니다. 타입 안정성 언어는 코드가 사용할 수 있는 값의 타입을 명확하게 하도록 합니다. 만약 코드의 일부분이 `String`을 요구한다면, 실수로 `Int`를 전달할 수 없습니다. 

스위프트는 타입이 안전하기 때문에, 코드를 컴파일할 때 타입 체크를 실시하고, 모든 일치하지 않는 타입은 오류로 표시합니다. 이것으로 인해 개발 과정에서 가능한 한 빨리 오류를 발견하고 고칠 수 있습니다. 

타입 체크는 다른 타입의 값들을 가지고 일할 때 오류를 피하도록 도와줍니다. 그러나, 이것이 선언한 모든 상수와 변수의 타입을 지정해줘야 한다는 의미는 아닙니다. 만약 필요한 값의 타입을 지정해주지 않는다면, 스위프트가 타입 추론을 이용하여 적절한 타입을 지정해줄 것입니다. 타입 추론을 사용하면 컴파일러는 코드를 컴파일 하는 과정에서 단순히 제공한 값을 검사하여 특정한 표현식의 타입을 자동적으로 추론할 수 있습니다. 

타입 추론 덕분에, 스위프트는 C나 Objective-C 같은 언어보다 더 적게 타입 명시를 해도 됩니다. 상수와 변수는 여전히 명시적으로 타입이 지정되지만, 그 타입들을 지정하는 일의 대부분은 스위프트가 수행합니다.

타입 추론은 특히 초기값과 함께 상수나 변수를 선언할 때 유용합니다. 이것은 가끔 상수나 변수를 선언할 때 그것에 리터럴 값 (또는 리터럴)을 할당하여 수행됩니다. (리터럴 값은 아래 예의  `42`와 `3.14159` 처럼 소스 코드에 직접적으로 나타나는 값입니다.)

예를 들어, `42`의 리터럴 값을 타입 지정 없이 새로운 상수에 할당하면, 그것을 정수로 보이는 숫자와 함께 초기화했기 때문에, 스위프트는 당신이 그 상수가 `Int`가 되길 바라는 거라고 추론할 것입니다: 

```swift
let meaningOfLife = 42
// meaningOfLife는 정수 타입으로 추론됩니다. 
```

마찬가지로, 만약 부동 소수점 리터럴에 타입을 지정하지 않으면, 스위프트는 `Double`을 생성하기를 원한다고 추론할 것입니다:

```swift
let pi = 3.14159
// pi는 더블 타입으로 추론됩니다. 
```

스위프트는 부동 소수점 숫자의 타입을 추론할 때, 항상 (`Float` 보다는) `Double` 을 선택합니다.

만약 한 표현식에서 정수와 부동 소수점 리터럴을 결합하면, 타입은 맥락상 `Double`로 추론될 것입니다:

```swift
let anotherPi = 3 + 0.14159
// anotherPi 또한 더블로 추론됩니다.
```

리터럴 값 `3`은 그 스스로는 명시적인 타입을 가지고 있지 않으므로, `Double`의 적절한 출력 타입은 덧셈의 일부인 부동 소수점 리터럴의 존재로부터 추론됩니다. 

---

_* deduce : 추론하다_</br>

---

</details>
</details>