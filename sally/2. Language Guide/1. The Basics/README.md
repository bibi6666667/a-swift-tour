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
_* at all : 조금도, 조금도 \~아니다_</br>
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

<details>
	<summary>Numeric Literals</summary>

## [Numeric Literals](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=of%20the%20addition.-,Numeric%20Literals,-Integer%20literals%20can)

Integer literals can be written as:

- A *decimal* number, with no prefix
- A *binary* number, with a `0b` prefix
- An *octal* number, with a `0o` prefix
- A *hexadecimal* number, with a `0x` prefix

All of these integer literals have a decimal value of `17`:

```swift
let decimalInteger = 17
let binaryInteger = 0b10001       // 17 in binary notation
let octalInteger = 0o21           // 17 in octal notation
let hexadecimalInteger = 0x11     // 17 in hexadecimal notation
```

Floating-point literals can be decimal (with no prefix), or hexadecimal (with a `0x` prefix). They must always have a number (or hexadecimal number) on both sides of the decimal point. Decimal floats can also have an optional *exponent*, indicated by an uppercase or lowercase `e`; hexadecimal floats must have an exponent, indicated by an uppercase or lowercase `p`.

For decimal numbers with an exponent of `exp`, the base number is multiplied by 10<sup>exp</sup>:

- `1.25e2` means 1.25 x 10<sup>2</sup>, or `125.0`.
- `1.25e-2` means 1.25 x 10<sup>-2</sup>, or `0.0125`.

For hexadecimal numbers with an exponent of `exp`, the base number is multiplied by 2<sup>exp</sup>:

- `0xFp2` means 15 x 2<sup>2</sup>, or `60.0`.
- `0xFp-2` means 15 x 2<sup>-2</sup>, or `3.75`.

All of these floating-point literals have a decimal value of `12.1875`:

```swift
let decimalDouble = 12.1875
let exponentDouble = 1.21875e1
let hexadecimalDouble = 0xC.3p0
```

Numeric literals can contain extra formatting to make them easier to read. Both integers and floats can be padded with extra zeros and can contain underscores to help with readability. Neither type of formatting affects the underlying value of the literal:

```swift
let paddedDouble = 000123.456
let oneMillion = 1_000_000
let justOverOneMillion = 1_000_000.000_000_1
```

---

## 숫자 리터럴

정수 리터럴은 다음과 같이 쓸 수 있습니다:

- 접두사가 없는 *10*진수
- `0b` 접두사가 있는 *2*진수
- `0o` 접두사가 있는 *8*진수
- `0x` 접두사가 있는 *16*진수

이 정수 리터럴 전부 `17`의 10진수 값을 가지고 있습니다:

```swift
let decimalInteger = 17
let binaryInteger = 0b10001       // 2진수에 17의 표기법
let octalInteger = 0o21           // 8진수에 17의 표기법
let hexadecimalInteger = 0x11     // 16진수에 17의 표기법
```

부동 소수점 리터럴은 (접두사 없이) 10진수거나 (`0x` 접두가사 있는) 16진수일 수 있습니다. 그것들에는 언제나 소수점 양쪽에 숫자 (혹은 16진수 숫자)가 있어야 합니다. 10진수 부동 소수점은 대문자 혹은 소문자 `e`로 표현하는 선택적 지수를 가질 수도 있습니다; 16진수 부동 소수점은  대문자 혹은 소문자 `p`로 표현하는 지수를 반드시 가져야만 합니다. 

지수가 `exp`인 10진수의 경우, 베이스 숫자에 10<sup>exp</sup>를 곱합니다:

- `1.25e2`는 1.25 x 10<sup>2</sup>, 혹은 `125.0`를 의미합니다.
- `1.25e-2`는 1.25 x 10<sup>2</sup>, 혹은 `0.0125`를 의미합니다.

지수가 `exp`인 16진수의 경우, 베이스 숫자에 2<sup>exp</sup> 곱합니다:

- `0xFp2` means 15 x 2<sup>2</sup>, or `60.0`.
- `0xFp-2` means 15 x 2<sup>-2</sup>, or `3.75`.

이 부동 소수점 리터럴 전부 `12.1875`의 10진수 값을 가지고 있습니다:

```swift
let decimalDouble = 12.1875
let exponentDouble = 1.21875e1
let hexadecimalDouble = 0xC.3p0
```

숫자 리터럴은 그것들을 더 읽기 쉽게 하기 위한 별도의 형식을 가지고 있을 수 있습니다. 가독성을 높이기 위해 정수와 부동 소수점은 추가적인 0을 넣거나, 밑줄을 포함할 수 있습니다. 두 형식 모두 리터럴의 기본 값에 영향을 주지 않습니다. 

```swift
let paddedDouble = 000123.456
let oneMillion = 1_000_000
let justOverOneMillion = 1_000_000.000_000_1
```

---

_* notation : 표기법_</br>
_* decimal point : 소수점_</br>
_* *exponent* : 멱지수_</br>
_* *pad* : 채워넣다_</br>
_* *underlying* : 밑에 있는, 기본적인_</br>

---

</details>

<details>
	<summary>Numeric Type Conversion</summary>

## [Numeric Type Conversion](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=let%20justOverOneMillion%20%3D%201_000_000.000_000_1-,Numeric%20Type%20Conversion,-Use%20the%20Int)

Use the `Int` type for all general-purpose integer constants and variables in your code, even if they’re known to be nonnegative. Using the default integer type in everyday situations means that integer constants and variables are immediately interoperable in your code and will match the inferred type for integer literal values.

Use other integer types only when they’re specifically needed for the task at hand, because of explicitly sized data from an external source, or for performance, memory usage, or other necessary optimization. Using explicitly sized types in these situations helps to catch any accidental value overflows and implicitly documents the nature of the data being used.

### Integer Conversion

The range of numbers that can be stored in an integer constant or variable is different for each numeric type. An `Int8` constant or variable can store numbers between `-128` and `127`, whereas a `UInt8` constant or variable can store numbers between `0` and `255`. A number that won’t fit into a constant or variable of a sized integer type is reported as an error when your code is compiled:

```swift
let cannotBeNegative: UInt8 = -1
// UInt8 can't store negative numbers, and so this will report an error
let tooBig: Int8 = Int8.max + 1
// Int8 can't store a number larger than its maximum value,
// and so this will also report an error
```

Because each numeric type can store a different range of values, you must opt in to numeric type conversion on a case-by-case basis. This opt-in approach prevents hidden conversion errors and helps make type conversion intentions explicit in your code.

To convert one specific number type to another, you initialize a new number of the desired type with the existing value. In the example below, the constant `twoThousand` is of type `UInt16`, whereas the constant `one` is of type `UInt8`. They can’t be added together directly, because they’re not of the same type. Instead, this example calls `UInt16(one)` to create a new `UInt16` initialized with the value of `one`, and uses this value in place of the original:

```swift
let twoThousand: UInt16 = 2_000
let one: UInt8 = 1
let twoThousandAndOne = twoThousand + UInt16(one)
```

Because both sides of the addition are now of type `UInt16`, the addition is allowed. The output constant (`twoThousandAndOne`) is inferred to be of type `UInt16`, because it’s the sum of two `UInt16` values.

`SomeType(ofInitialValue)` is the default way to call the initializer of a Swift type and pass in an initial value. Behind the scenes, `UInt16` has an initializer that accepts a `UInt8` value, and so this initializer is used to make a new `UInt16` from an existing `UInt8`. You can’t pass in *any* type here, however—it has to be a type for which `UInt16` provides an initializer. Extending existing types to provide initializers that accept new types (including your own type definitions) is covered in [Extensions](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html).

### Integer and Floating-Point Conversion

Conversions between integer and floating-point numeric types must be made explicit:

```swift
let three = 3
let pointOneFourOneFiveNine = 0.14159
let pi = Double(three) + pointOneFourOneFiveNine
// pi equals 3.14159, and is inferred to be of type Double
```

Here, the value of the constant `three` is used to create a new value of type `Double`, so that both sides of the addition are of the same type. Without this conversion in place, the addition would not be allowed.

Floating-point to integer conversion must also be made explicit. An integer type can be initialized with a `Double` or `Float` value:

```swift
let integerPi = Int(pi)
// integerPi equals 3, and is inferred to be of type Int
```

Floating-point values are always truncated when used to initialize a new integer value in this way. This means that `4.75` becomes `4`, and `-3.9` becomes `-3`.

> NOTE
>
> The rules for combining numeric constants and variables are different from the rules for numeric literals. The literal value `3` can be added directly to the literal value `0.14159`, because number literals don’t have an explicit type in and of themselves. Their type is inferred only at the point that they’re evaluated by the compiler.

---

## 숫자 타입 변환

코드에서 일반적인 목적을 가지고 있는 모든 정수 상수와 변수의 타입은, 그것들이 음수가 아니라는 것을 알고 있더라도 `Int`를 사용하십시오. 모든 상황에서 기본 정수 타입을 사용하면 정수 상수와 변수가 코드 안에서 즉시 상호 운용할 수 있고, 정수 리털값을 유츄한 타입과 일치할 것입니다. 

당면한 과제에 외부로부터의 명시적인 크기의 데이터가 있거나, 성능, 메모리 사용량, 혹은 다른 필요한 최적화 때문에 특별히 필요한 경우에만 다른 정수 타입을 사용하십시오. 이런 상황에서 명시적인 크기의 타입을 사용하는 것은, 갑작스러운 값 오버플로우를 잡는 것과, 사용되는 데이터의 특성을 암묵적으로 문서화하는데 도움이 됩니다. 

### 정수 변환

정수 상수나 변수에 저장할 수 있는 숫자의 법위는 각 숫자 타입에 따라 다릅니다. `Int8` 상수나 변수는 `-128`과 `127` 사이의 숫자를 저장할 수 있는 반면, `UInt8` 상수나 변수는 `0`과 `255` 사이의 숫자를 저장할 수 있습니다. 크기가 지정된 정수 타입의 상수나 변수에 맞지 않는 숫자는 코드가 컴파일 될 때 오류로 보고됩니다:

```swift
let cannotBeNegative: UInt8 = -1
// UInt8은 음수를 저장할 수 없기 때문에, 오류로 보고될 것입니다
let tooBig: Int8 = Int8.max + 1
// Int8은 그 최대값보다 더 큰 숫자를 저장할 수 없기 때문에, 이것 또한 오류로 보고될 것입니다
```

각 숫자 타입은 저장할 수 있는 값의 범위가 다르기 때문에, 경우에 따라 숫자 타입 변환을 선택해야 합니다. 이런 옵트인 접근법은 숨겨진 전환 오류를 예방하고, 타입 변환의 의도가 코드에서 명시적이도록 해줍니다.

하나의 특정한 숫자 타입을 다른 것으로 변환하기 위해서는, 기존값과 함께 요구되는 타입으로 새로운 숫자를 초기화해야 합니다. 아래 예에서, 정수 `twoThousand`는 `UInt16` 타입인 반면에 `one`은  `UInt8` 타입입니다. 그들은 같은 타입이 아니기 때문에 바로 더할 수는 없습니다. 대신에, 이 예는 값 `one`과 함께 초기화된 새로운 `UInt16`를 만들기 위해 `UInt16(one)`를 호출하고 원래 것 대신에 사용합니다. 

```swift
let twoThousand: UInt16 = 2_000
let one: UInt8 = 1
let twoThousandAndOne = twoThousand + UInt16(one)
```

덧셈의 양쪽이 현재 `UInt16` 타입이기 때문에, 덧셈은 허락됩니다. 결과 상수(`twoThousandAndOne`)는 두 개의 `UInt16` 값의 합이기 때문에 `UInt16` 타입으로 추론됩니다. 

`SomeType(ofInitialValue)`은 스위프트 타입의 생성자를 호출하고 초기값을 전달하는 기본적인 방법입니다. 이면에서는, `UInt16`는 `UInt8` 값을 허용하는 생성자가 있으므로, 이 생성자는 기존의 `UInt8`로부터 새로운 `UInt16`를 만드는데 사용됩니다. 하지만, 여기에 *any* 타입을 전달할 수는 없습니다. `UInt16`가 생성자를 제공하는 타입이어야 합니다. (본인만의 타입 정의를 포함하여) 새로운 타입을 허용하는 생성자를 제공하기 위해 기존의 타입을 확장하는 것은 [Extensions](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html)에서 다룹니다.

### 정수와 부동 소수점 변환

정수와 부동 소수점 숫자 타입 사이의 변환은 명시적으로 이루어져야 합니다:

```swift
let three = 3
let pointOneFourOneFiveNine = 0.14159
let pi = Double(three) + pointOneFourOneFiveNine
// pi의 값은 3.14159이고 Double 타입으로 유추됩니다. 
```

여기서, 상수 `three`의 값은 새로운 `Double` 타입의 값을 만들기 위해 사용되었기 때문에, 더해지는 양쪽 모두 같은 타입이 됩니다. 이 변환이 없으면 더할 수 없습니다. 

부동 소수점에서 정수로의 변환 또한 명시적으로 이루어져야 합니다. 정수 타입은 `Double` 혹은 `Float` 값으로 초기화될 수 있습니다:

```swift
let integerPi = Int(pi)
// integerPi의 값은 3이고 Int 타입으로 유추됩니다. 
```

부동 소수점 값은 이런 식으로 새로운 정수 값을 초기화하는데 사용될 때, 항상 잘립니다. 이 말은 `4.75`는 `4`가 되고 `-3.9`는 `-3`이 된다는 의미입니다.

> 노트
>
> 숫자 상수와 변수의 결합 규칙은 숫자 리러털에서의 규칙과 다릅니다. 숫자 리터럴은 그들 스스로는 명시적인 타입이 없기 때문에, 리터럴 값 `3`은 리터럴 값 `0.14159`와 바로 더해질 수 있습니다. 그들의 타입은 컴파일러에 의해 평가되는 시점에서만 유추됩니다. 

---

_* interoperable : 상호 운용 가능한_</br>
_* at hand : 당면한_</br>
_* opt : 고르다, 선택하다_</br>
_* intention : 의도_</br>
_* in place : 제자리에, 올바른 곳에_</br>
_* truncate : 자르다_</br>

---

</details>

<details>
	<summary>Type Aliases</summary>

## [Type Aliases](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=by%20the%20compiler.-,Type%20Aliases,-Type%20aliases%20define)

*Type aliases* define an alternative name for an existing type. You define type aliases with the `typealias` keyword.

Type aliases are useful when you want to refer to an existing type by a name that’s contextually more appropriate, such as when working with data of a specific size from an external source:

```swift
typealias AudioSample = UInt16
```

Once you define a type alias, you can use the alias anywhere you might use the original name:

```swift
var maxAmplitudeFound = AudioSample.min
// maxAmplitudeFound is now 0
```

Here, `AudioSample` is defined as an alias for `UInt16`. Because it’s an alias, the call to `AudioSample.min` actually calls `UInt16.min`, which provides an initial value of `0` for the `maxAmplitudeFound` variable.

---

## 타입 별칭

*타입 별칭*은 기존 타입을 대체 이름을 정의합니다. `typealias` 키워드를 사용하여 타입 별칭을 정의합니다. 

타입 별칭은 외부 소스로부터의 특정한 크기의 데이터를 사용할 때 같은, 맥락적으로 더 적절한 이름으로 기존의 타입을 참조하고 싶을 때 유용합니다:

```swift
typealias AudioSample = UInt16
```

한번 타입 별칭을 정의하면, 원래 이름을 사용했었을 어디에서나 별칭을 사용할 수 있습니다:

```swift
var maxAmplitudeFound = AudioSample.min
// maxAmplitudeFound은 현재 0 입니다.
```

여기서,`AudioSample`은  `UInt16`의 별칭으로 정의되었습니다. 별칭이기 때문에, `AudioSample.min`을 호출하는 것은 실제로 `maxAmplitudeFound` 변수에 초기값 `0`을 제공하는, `UInt16.min`를 호출합니다.

---

_* alternative : 대안, 대체_</br>

---

</details>

<details>
	<summary>Booleans</summary>

## [Booleans](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=the%20maxAmplitudeFound%20variable.-,Booleans,-Swift%20has%20a)

Swift has a basic *Boolean* type, called `Bool`. Boolean values are referred to as *logical*, because they can only ever be true or false. Swift provides two Boolean constant values, `true` and `false`:

```swift
let orangesAreOrange = true
let turnipsAreDelicious = false
```

The types of `orangesAreOrange` and `turnipsAreDelicious` have been inferred as `Bool` from the fact that they were initialized with Boolean literal values. As with `Int` and `Double` above, you don’t need to declare constants or variables as `Bool` if you set them to `true` or `false` as soon as you create them. Type inference helps make Swift code more concise and readable when it initializes constants or variables with other values whose type is already known.

Boolean values are particularly useful when you work with conditional statements such as the `if` statement:

```swift
if turnipsAreDelicious {
    print("Mmm, tasty turnips!")
} else {
    print("Eww, turnips are horrible.")
}
// Prints "Eww, turnips are horrible."
```

Conditional statements such as the `if` statement are covered in more detail in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

Swift’s type safety prevents non-Boolean values from being substituted for `Bool`. The following example reports a compile-time error:

```swift
let i = 1
if i {
    // this example will not compile, and will report an error
}
```

However, the alternative example below is valid:

```swift
let i = 1
if i == 1 {
    // this example will compile successfully
}
```

The result of the `i == 1` comparison is of type `Bool`, and so this second example passes the type-check. Comparisons like `i == 1` are discussed in [Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html).

As with other examples of type safety in Swift, this approach avoids accidental errors and ensures that the intention of a particular section of code is always clear.

---

## 부울

스위프트는 `Bool` 이라는 기본 *부울* 타입이 있습니다. 부울 값은 참이나 거짓만 될 수 있기 때문에, *논리 값*이라고 합니다. 스위프트는 `true`와 `false` 두 가지 부울 상수값을 제공합니다: 

```swift
let orangesAreOrange = true
let turnipsAreDelicious = false
```

`orangesAreOrange`와 `turnipsAreDelicious`의 타입은 부울 리터럴 값으로 초기화 되었다는 사실로부터, `Bool`로 추론됩니다. 위의 `Int`와 `Double`에서 처럼, 그들을 생성하자 마자 `true`나 `false`로 설정했다면, 그 상수나 변수를 `Bool`로 선언할 필요가 없습니다. 타입 추론은, 이미 타입을 알고 있는 다른 값으로 상수나 변수를 초기화할 때, 스위프트 코드를 더욱 간결하고 읽기 쉽게 도와줍니다. 

부울 값은 `if`문 같은 조건문과 함께 사용할 때, 특히 유용합니다:

```swift
if turnipsAreDelicious {
    print("Mmm, tasty turnips!")
} else {
    print("Eww, turnips are horrible.")
}
// "Eww, turnips are horrible." 출력
```

`if`문 같은 조건문은 [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)에서 더 자세히 다룹니다. 

스위프트의 타입 안정성은 부울이 아닌 값이 `Bool`을 대체하는 것을 방지합니다. 다음의 예는 컴파일 타임 오류를 보고합니다:

```swift
let i = 1
if i {
    // 이 예는 컴파일 되지 않을 것이고, 오류를 보고할 것입니다. 
}
```

그러나, 아래의 대안 예는 유효합니다:

```swift
let i = 1
if i == 1 {
    // 이 예는 성공적으로 컴파일 될 것입니다. 
}
```

`i == 1` 비교의 결과는 `Bool` 타입이기 때문에, 이 두번째 예는 타입 체크를 통과합니다. `i == 1` 같은 비교는 [Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html)에서 설명합니다. 

스위프트의 타입 안정성의 다른 예처럼, 이 접근은 우발적인 오류를 방지하고, 코드의 특정 구역의 의도가 언제나 명확하도록 해줍니다. 

---

_* concise : 간결한_</br>
_* substitute : 바꾸다, 역할을 대신하다_</br>
_* intention : 의도_</br>

---

</details>

<details>
	<summary>Tuples</summary>

## [Tuples](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=is%20always%20clear.-,Tuples,-Tuples%20group%20multiple)

*Tuples* group multiple values into a single compound value. The values within a tuple can be of any type and don’t have to be of the same type as each other.

In this example, `(404, "Not Found")` is a tuple that describes an *HTTP status code*. An HTTP status code is a special value returned by a web server whenever you request a web page. A status code of `404 Not Found` is returned if you request a webpage that doesn’t exist.

```swift
let http404Error = (404, "Not Found")
// http404Error is of type (Int, String), and equals (404, "Not Found")
```

The `(404, "Not Found")` tuple groups together an `Int` and a `String` to give the HTTP status code two separate values: a number and a human-readable description. It can be described as “a tuple of type `(Int, String)`”.

You can create tuples from any permutation of types, and they can contain as many different types as you like. There’s nothing stopping you from having a tuple of type `(Int, Int, Int)`, or `(String, Bool)`, or indeed any other permutation you require.

You can *decompose* a tuple’s contents into separate constants or variables, which you then access as usual:

```swift
let (statusCode, statusMessage) = http404Error
print("The status code is \(statusCode)")
// Prints "The status code is 404"
print("The status message is \(statusMessage)")
// Prints "The status message is Not Found"
```

If you only need some of the tuple’s values, ignore parts of the tuple with an underscore (`_`) when you decompose the tuple:

```swift
let (justTheStatusCode, _) = http404Error
print("The status code is \(justTheStatusCode)")
// Prints "The status code is 404"
```

Alternatively, access the individual element values in a tuple using index numbers starting at zero:

```swift
print("The status code is \(http404Error.0)")
// Prints "The status code is 404"
print("The status message is \(http404Error.1)")
// Prints "The status message is Not Found"
```

You can name the individual elements in a tuple when the tuple is defined:

```swift
let http200Status = (statusCode: 200, description: "OK")
```

If you name the elements in a tuple, you can use the element names to access the values of those elements:

```swift
print("The status code is \(http200Status.statusCode)")
// Prints "The status code is 200"
print("The status message is \(http200Status.description)")
// Prints "The status message is OK"
```

Tuples are particularly useful as the return values of functions. A function that tries to retrieve a web page might return the `(Int, String)` tuple type to describe the success or failure of the page retrieval. By returning a tuple with two distinct values, each of a different type, the function provides more useful information about its outcome than if it could only return a single value of a single type. For more information, see [Functions with Multiple Return Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID164).

> NOTE
>
> Tuples are useful for simple groups of related values. They’re not suited to the creation of complex data structures. If your data structure is likely to be more complex, model it as a class or structure, rather than as a tuple. For more information, see [Structures and Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html).

---

## 튜플

*튜플*은 여러 개의 값을 하나의 혼합 값으로 묶습니다. 튜플안의 값들은 어떤 타입이어도 상관없고, 서로 같은 타입일 필요도 없습니다. 

예를 들어, `(404, "Not Found")`는 *HTTP 상태 코드*를 설명하는 튜플입니다. HTTP 상태 코드는 웹 페이지를 요청할 때마다, 웹 서버로부터 반환되는 특별한 값입니다. 존재하지 않는 웹 페이지를 요청하면 상태 코드 `404 Not Found`가 반환됩니다. 

```swift
let http404Error = (404, "Not Found")
// http404Error는 (Int, String) 타입이고, (404, "Not Found")의 값을 가집니다.
```

`(404, "Not Found")` 튜플은 HTTP 상태 코드에 두 개의 분리된 값(숫자와 사람이 읽을 수 있는 설명)을 주기 위해 `Int`와 `String`을 함께 묶습니다. 이것은 "`(Int, String)` 타입의 튜플" 이라고 말할 수 있습니다.

어떤 타입의 순열로도 튜플을 만들 수 있고, 원하는 만큼 많은 다른 타입을 포함할 수 있습니다. `(Int, Int, Int)`, 혹은 `(String, Bool)`, 혹은 정말로 필요한 다른 어떤 순열의 타입으로 튜플을 만드는 것을 막을 수 있는 것은 없습니다. 

튜플의 내용물을 분리된 상수와 변수로 *분해*한 후에, 평소처럼 접근할 수 있습니다:

```swift
let (statusCode, statusMessage) = http404Error
print("The status code is \(statusCode)")
// "The status code is 404" 출력
print("The status message is \(statusMessage)")
// "The status message is Not Found" 출력
```

만약 튜플의 값 중 일부만 필요하다면, 튜플을 분해할 때 밑줄 (`_`)을 사용하여 튜플의 일부분을 무시하십시오:

```swift
let (justTheStatusCode, _) = http404Error
print("The status code is \(justTheStatusCode)")
// "The status code is 404" 출력
```

다른 방법으로, 0 부터 시작하는 인덱스 숫자를 이용하여 튜플의 개별 요소 값에 접근하십시오:

```swift
print("The status code is \(http404Error.0)")
// Prints "The status code is 404"
print("The status message is \(http404Error.1)")
// Prints "The status message is Not Found"
```

튜플이 정의될 때, 튜플의 개별 요소에 이름을 붙일 수 있습니다:

```swift
let http200Status = (statusCode: 200, description: "OK")
```

튜플의 요소에 이름을 붙이면, 그 요소의 이름을 통해 해당 요소의 값에 접근할 수 있습니다:

```swift
print("The status code is \(http200Status.statusCode)")
// "The status code is 200" 출력
print("The status message is \(http200Status.description)")
// "The status message is OK" 출력
```

튜플은 함수의 반환 값으로 특히 유용합니다. 웹 페이지에 검색을 시도하는 함수는, 페이지 검색의 성공 혹은 실패를 설명하기 위해 `(Int, String)` 튜플 타입을 반환할 것입니다. 각각 다른 타입을 가지고 있는, 두 개별 값으로 튜플을 반환함으로써, 함수는 단일 타입의 단일 값만을 반환하는 것보다, 그것의 결과에 대해 더 유용한 정보를 제공합니다. 더 많은 정보는 [Functions with Multiple Return Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID164)를 보십시오.

> 노트
>
> 튜플은 연관된 값의 간단한 그룹에 유용합니다. 그것들은 복잡한 데이터 구조 생성에 적합하지 않습니다. 만약 데이터 구조가 더 복잡할 것 같다면, 튜플 보다는 클래스나 구조체로 그것을 모델링 하십시오. 더 많은 정보는  [Structures and Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html)를 보십시오.

---

_* permutation : 순열_</br>
_* indeed : 실제로, 참으로_</br>
_* *decompose* : 분해하다_</br>
_* *as usual* : 평소처럼_</br>
_* *retrieve* : 검색하다_</br>

---

</details>

<details>
	<summary>Optionals</summary>

## [Optionals](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#:~:text=Structures%20and%20Classes.-,Optionals,-You%20use%20optionals)

You use *optionals* in situations where a value may be absent. An optional represents two possibilities: Either there *is* a value, and you can unwrap the optional to access that value, or there *isn’t* a value at all.

> NOTE
>
> The concept of optionals doesn’t exist in C or Objective-C. The nearest thing in Objective-C is the ability to return `nil` from a method that would otherwise return an object, with `nil` meaning “the absence of a valid object.” However, this only works for objects—it doesn’t work for structures, basic C types, or enumeration values. For these types, Objective-C methods typically return a special value (such as `NSNotFound`) to indicate the absence of a value. This approach assumes that the method’s caller knows there’s a special value to test against and remembers to check for it. Swift’s optionals let you indicate the absence of a value for *any type at all*, without the need for special constants.

Here’s an example of how optionals can be used to cope with the absence of a value. Swift’s `Int` type has an initializer which tries to convert a `String` value into an `Int` value. However, not every string can be converted into an integer. The string `"123"` can be converted into the numeric value `123`, but the string `"hello, world"` doesn’t have an obvious numeric value to convert to.

The example below uses the initializer to try to convert a `String` into an `Int`:

```swift
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)
// convertedNumber is inferred to be of type "Int?", or "optional Int"
```

Because the initializer might fail, it returns an *optional* `Int`, rather than an `Int`. An optional `Int` is written as `Int?`, not `Int`. The question mark indicates that the value it contains is optional, meaning that it might contain *some* `Int` value, or it might contain *no value at all*. (It can’t contain anything else, such as a `Bool` value or a `String` value. It’s either an `Int`, or it’s nothing at all.)

### nil

You set an optional variable to a valueless state by assigning it the special value `nil`:

```swift
var serverResponseCode: Int? = 404
// serverResponseCode contains an actual Int value of 404
serverResponseCode = nil
// serverResponseCode now contains no value
```

> NOTE
>
> You can’t use `nil` with non-optional constants and variables. If a constant or variable in your code needs to work with the absence of a value under certain conditions, always declare it as an optional value of the appropriate type.

If you define an optional variable without providing a default value, the variable is automatically set to `nil` for you:

```swift
var surveyAnswer: String?
// surveyAnswer is automatically set to nil
```

> NOTE
>
> Swift’s `nil` isn’t the same as `nil` in Objective-C. In Objective-C, `nil` is a pointer to a nonexistent object. In Swift, `nil` isn’t a pointer—it’s the absence of a value of a certain type. Optionals of *any* type can be set to `nil`, not just object types.

### If Statements and Forced Unwrapping

You can use an `if` statement to find out whether an optional contains a value by comparing the optional against `nil`. You perform this comparison with the “equal to” operator (`==`) or the “not equal to” operator (`!=`).

If an optional has a value, it’s considered to be “not equal to” `nil`:

```swift
if convertedNumber != nil {
    print("convertedNumber contains some integer value.")
}
// Prints "convertedNumber contains some integer value."
```

Once you’re sure that the optional *does* contain a value, you can access its underlying value by adding an exclamation point (`!`) to the end of the optional’s name. The exclamation point effectively says, “I know that this optional definitely has a value; please use it.” This is known as *forced unwrapping* of the optional’s value:

```swift
if convertedNumber != nil {
    print("convertedNumber has an integer value of \(convertedNumber!).")
}
// Prints "convertedNumber has an integer value of 123."
```

For more about the `if` statement, see [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

> NOTE
>
> Trying to use `!` to access a nonexistent optional value triggers a runtime error. Always make sure that an optional contains a non-`nil` value before using `!` to force-unwrap its value.

### Optional Binding

You use *optional binding* to find out whether an optional contains a value, and if so, to make that value available as a temporary constant or variable. Optional binding can be used with `if` and `while` statements to check for a value inside an optional, and to extract that value into a constant or variable, as part of a single action. `if` and `while` statements are described in more detail in [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

Write an optional binding for an `if` statement as follows:

```swift
if let constantName = someOptional {
    statements
}
```

You can rewrite the `possibleNumber` example from the [Optionals](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID330) section to use optional binding rather than forced unwrapping:

```swift
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

```swift
if let firstNumber = Int("4"), let secondNumber = Int("42"), firstNumber < secondNumber && secondNumber < 100 {
    print("\(firstNumber) < \(secondNumber) < 100")
}
// Prints "4 < 42 < 100"

if let firstNumber = Int("4") {
    if let secondNumber = Int("42") {
        if firstNumber < secondNumber && secondNumber < 100 {
            print("\(firstNumber) < \(secondNumber) < 100")
        }
    }
}
// Prints "4 < 42 < 100"
```

> NOTE
>
> Constants and variables created with optional binding in an `if` statement are available only within the body of the `if` statement. In contrast, the constants and variables created with a `guard` statement are available in the lines of code that follow the `guard` statement, as described in [Early Exit](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html#ID525).

### Implicitly Unwrapped Optionals

As described above, optionals indicate that a constant or variable is allowed to have “no value”. Optionals can be checked with an `if` statement to see if a value exists, and can be conditionally unwrapped with optional binding to access the optional’s value if it does exist.

Sometimes it’s clear from a program’s structure that an optional will *always* have a value, after that value is first set. In these cases, it’s useful to remove the need to check and unwrap the optional’s value every time it’s accessed, because it can be safely assumed to have a value all of the time.

These kinds of optionals are defined as *implicitly unwrapped optionals*. You write an implicitly unwrapped optional by placing an exclamation point (`String!`) rather than a question mark (`String?`) after the type that you want to make optional. Rather than placing an exclamation point after the optional’s name when you use it, you place an exclamation point after the optional’s type when you declare it.

Implicitly unwrapped optionals are useful when an optional’s value is confirmed to exist immediately after the optional is first defined and can definitely be assumed to exist at every point thereafter. The primary use of implicitly unwrapped optionals in Swift is during class initialization, as described in [Unowned References and Implicitly Unwrapped Optional Properties](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html#ID55).

An implicitly unwrapped optional is a normal optional behind the scenes, but can also be used like a non-optional value, without the need to unwrap the optional value each time it’s accessed. The following example shows the difference in behavior between an optional string and an implicitly unwrapped optional string when accessing their wrapped value as an explicit `String`:

```swift
let possibleString: String? = "An optional string."
let forcedString: String = possibleString! // requires an exclamation point

let assumedString: String! = "An implicitly unwrapped optional string."
let implicitString: String = assumedString // no need for an exclamation point
```

You can think of an implicitly unwrapped optional as giving permission for the optional to be force-unwrapped if needed. When you use an implicitly unwrapped optional value, Swift first tries to use it as an ordinary optional value; if it can’t be used as an optional, Swift force-unwraps the value. In the code above, the optional value `assumedString` is force-unwrapped before assigning its value to `implicitString` because `implicitString` has an explicit, non-optional type of `String`. In code below, `optionalString` doesn’t have an explicit type so it’s an ordinary optional.

```swift
let optionalString = assumedString
// The type of optionalString is "String?" and assumedString isn't force-unwrapped.
```

If an implicitly unwrapped optional is `nil` and you try to access its wrapped value, you’ll trigger a runtime error. The result is exactly the same as if you place an exclamation point after a normal optional that doesn’t contain a value.

You can check whether an implicitly unwrapped optional is `nil` the same way you check a normal optional:

```swift
if assumedString != nil {
    print(assumedString!)
}
// Prints "An implicitly unwrapped optional string."
```

You can also use an implicitly unwrapped optional with optional binding, to check and unwrap its value in a single statement:

```swift
if let definiteString = assumedString {
    print(definiteString)
}
// Prints "An implicitly unwrapped optional string."
```

> NOTE
>
> Don’t use an implicitly unwrapped optional when there’s a possibility of a variable becoming `nil` at a later point. Always use a normal optional type if you need to check for a `nil` value during the lifetime of a variable.

---

## 옵셔널

옵셔널은 값이 없을 수도 있는 상황에서 사용합니다. 옵셔널은 두가지 가능성을 나타냅니다: 값이 있고, 그 값에 접근하기 위해 옵셔널을 벗길 수 있거나, 혹은 값이 아예 없는 것입니다. 

> 노트
>
> 옵셔널의 개념은 C나 Objective-C에는 없습니다. Objective-C에서 가장 비슷한 것은, 객체를 반환할 메소드로부터 `nil`을 반환하는 기능입니다. `nil`은 "유효한 객체의 부재"를 의미합니다. 그러나, 이것은 객체에만 적용되고, 구조체, 기본 C 타입들, 혹은 열거형 값들에는 적용되지 않습니다. 이러한 타입들을 위해서 Objective-C 메소드는 값의 부재를 알리기 위해 일반적으로 (`NSNotFound` 같은) 특별한 값을 반환합니다. 이러한 접근법은 메소드 호출자가 테스트할 특별한 값이 있다는 것을 알고, 그것을 체크하는 것을 기억한다고 가정합니다. 스위프트의 옵셔널은 특별한 상수의 도움 없이도, 모든 타입에 대해 값의 부재를 나타낼 수 있습니다.

여기 값의 부재에 대처하기 위해 옵셔널이 어떻게 사용되는지에 대한 예가 있습니다. 스위프트의 `Int` 타입은 `String` 값에서  `Int` 값으로의 변환을 시도하는 이니셜라이저를 가지고 있습니다. 그러나, 모든 문자열이 정수로 변환될 수 있는 것은 아닙니다. 문자열 `"123"`은  숫자 값 `123`으로 변환될 수 있지만, 문자열 `"hello, world"`는 변환될 명백한 숫자 값이 없습니다. 

아래의 예는 `String`에서 `Int`로의 변환을 시도하기 위해 이니셜라이저를 사용합니다:

```swift
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)
// convertedNumber은 "Int?", 혹은 "optional Int" 타입으로 추론됩니다. 
```

이니셜라이저가 실패할 수 있기 때문에, `Int`가 아니라 *옵셔널* `Int`를 반환합니다. 옵셔널 `Int`는 `Int`이 아니라  `Int?`라고 씁니다. 물음표는 그것이 포함하고 있는 값이 옵셔널이라는 것을 알려줍니다. 그것이 *어떤* `Int` 값을 포함할 수도 있고, 전혀 값을 포함하지 않을 수도 있다는 것을 의미합니다. (그것은 `Bool` 값이나 `String` 값 같은 다른 것을 포함할 수는 없습니다. `Int`이거나 아무것도 아닙니다.)

### 닐

특별한 값인 `nil`을 할당하여, 옵셔널 변수를 값이 없는 상태로 설정할 수 있습니다:

```swift
var serverResponseCode: Int? = 404
// serverResponseCode는 진짜 정수값 404를 포함합니다. 
serverResponseCode = nil
// serverResponseCode는 이제 값이 없습니다. 
```

> 노트
>
> `nil`은 옵셔널이 아닌 상수, 변수와 함께 사용할 수 없습니다. 코드 안에 있는 상수나 변수가 특정한 조건 하에서 값의 부재를 사용해야 한다면, 항상 그것을 적절한 타입의 옵셔널 값으로 선언하십시오.

옵셔널 값에 디폴트 값을 제공하지 않고 정의했다면, 변수는 자동적으로 `nil`로 설정됩니다:

```swift
var surveyAnswer: String?
// surveyAnswer는 자동적으로 nil로 설정됩니다. 
```

> 노트
>
> 스위프트의 `nil`은 Objective-C의 `nil`과 다릅니다. Objective-C에서 `nil`은 존재하지 않는 객체의 포인터입니다. 스위프트에서 `nil`은 포인터가 아니고, 특정한 타입의 값의 부재입니다. *어떤* 타입의 옵셔널도 객체 타입 뿐만 아니라 `nil`로 설정할 수 있습니다. 

### If문과 강제 언래핑

`if`문을 사용하여 옵셔널을 `nil`에 대해 비교해서 옵셔널이 값을 포함하고 있는지 알아낼 수 있습니다. "일치" 연산자(`==`) 혹은 "불일치"연산자(`!=`)로 이 비교를 수행합니다.

옵셔널이 값을 가지고 있다면, 그것은 `nil`에 대해 "불일치"라고 여겨집니다:

```swift
if convertedNumber != nil {
    print("convertedNumber contains some integer value.")
}
// "convertedNumber contains some integer value." 출력
```

한번 옵셔널이 값을 가지고 *있다고* 확신하면, 옵셔널의 이름 뒤에 느낌표(`!`)를 붙여서 그것의 기저값에 접근할 수 있습니다. 느낌표는 "나는 이 옵셔널은 확실히 값을 가지고 있다는 것을 알아; 그걸 사용해줘"라고 효과적으로 말합니다. 이것이 옵셔널 값의 강제 언래핑입니다:

```swift
if convertedNumber != nil {
    print("convertedNumber has an integer value of \(convertedNumber!).")
}
// "convertedNumber has an integer value of 123." 출력
```

`if`문에 대한 더 자세한 것은 [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)를 보십시오..

> 노트
>
> 존재하지 않는 옵셔널 값에 접근하기 위해 `!`를 사용하는 것은 런타임 오류를 일으킵니다. 항상 `!`를 사용하여 값을 강제 언래핑하기 전에 옵셔널이 `nil`이 아닌 값을 포함하고 있다는 것을 확실히 하십시오.

### 옵셔널 바인딩

옵셔널 바인딩을 사용하여, 옵셔널이 값을 가지고 있는지 알아내고, 그 값을 임시 상수나 변수로 사용할 수 있도록 합니다. 단일 동작의 일부로써, 옵셔널 안의 값을 확인하고, 그 값을 상수나 변수로 추출하기 위해 옵셔널 바인딩을 `if`문, `while`문과 함께 사용합니다. `if`문과 `while`문에 대한 자세한 내용은 [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)에 설명되어 있습니다.

`if`문을 사용하여 다음과 같이 옵셔널 바인딩을 작성하세요:

```swift
if let constantName = someOptional {
    statements
}
```

강제 언래핑 말고 옵셔널 바인딩을 사용하여 [Optionals](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID330) 영역의 `possibleNumber` 예제를 재작성할 수 있습니다:

```swift
if let actualNumber = Int(possibleNumber) {
    print("The string \"\(possibleNumber)\" has an integer value of \(actualNumber)")
} else {
    print("The string \"\(possibleNumber)\" couldn't be converted to an integer")
}
// "The string "123" has an integer value of 123" 출력
```

이 코드는 이렇게 읽을 수 있습니다:

"`Int(possibleNumber)`에 의해 반환된 옵셔널 `Int`가 값을 포함하고 있다면, `actualNumber`라는 이름의 새로운 상수를 옵셔널이 포함된 값으로 설정하십시오."

변환이 성공적이라면, `actualNumber` 상수는 `if`문의 첫번째 분기 내에서 사용 가능해집니다. 그것은 이미 옵셔널에 포함된 값으로 초기화되었기 때문에, 그 값에 접근하기 위해 `!`접미사를 사용할 필요가 없습니다. 이 예에서, `actualNumber`는 단순히 변환의 결과를 출력하는데 사용됩니다.  

상수와 변수 모두 옵셔널 바인딩과 함께 사용할 수 있습니다. `if`문에서 첫번째 분기 내에서 `actualNumber`의 값을 다루고 싶다면, 대신 `if var actualNumber`를 작성할 수 있고, 옵셔널 내의 포함된 값은 상수 보다는 변수로 사용할 수 있습니다.

단일 `if`문 안에 옵셔널 바인딩과 부울 조건을, 반점으로 구분하여, 필요한 만큼 포함할 수 있습니다. 옵셔널 바인딩 안의 어떠한 값이 `nil`이거나 어떠한 부울 조건이 `false`라고 평가되면, 전체 `if`문의 조건은 `false`라고 간주됩니다. 다음의 `if`문은 동일합니다:

```swift
if let firstNumber = Int("4"), let secondNumber = Int("42"), firstNumber < secondNumber && secondNumber < 100 {
    print("\(firstNumber) < \(secondNumber) < 100")
}
// "4 < 42 < 100" 출력

if let firstNumber = Int("4") {
    if let secondNumber = Int("42") {
        if firstNumber < secondNumber && secondNumber < 100 {
            print("\(firstNumber) < \(secondNumber) < 100")
        }
    }
}
// "4 < 42 < 100" 출력
```

> 노트
>
> `if`문 안에서 옵셔널 바인딩과 함께 생성된 상수와 변수는 `if`의 바디 안에서만 사용 가능합니다. 대조적으로, `guard`문과 함께 생성된 상수와 변수는 [Early Exit](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html#ID525)에서 설명하는 것처럼, `guard`문 뒤에 따라오는 코드 라인 안에서 사용 가능합니다. 

### 암시적으로 언래핑된 옵셔널

위에서 설명한 것처럼, 옵셔널은 상수나 변수가 "값이 없음"을 가지는 것이 허락됐다는 것을 나타냅니다. 값이 존재하는지 확인하기 위해 `if`문을 사용하여 옵셔널을 확인할 수 있고, 그것이 존재한다면 그 옵셔널의 값에 접근하기 위해 옵셔널 바인딩을 사용하여 조건적으로 옵셔널을 언래핑 할 수 있습니다. 

때때로 프로그램의 구조로부터, 그 값이 처음 설정된 이후에, 옵셔널이 *언제나* 값을 가지고 있을 거라는 것을 명확하게 할 수 있습니다. 이러한 경우에, 그것이 언제나 값을 가지고 있을 것이라는 것을 안전하게 추측할 수 있기 때문에, 확인할 필요를 제거하고, 그것이 접근할 때마다 옵셔널의 값을 언래핑 하는데에 유용합니다. 

이러한 종류의 옵셔널을 *암시적으로 언래핑된 옵셔널*이라고 합니다. 옵셔널로 만들고 싶은 타입 뒤에 물음표(`String?`)를 붙이기 보다는 느낌표(`String!`)를 붙여서 암시적으로 언래핑된 옵셔널을 작성할 수 있습니다. 사용할 때 옵셔널의 이름 뒤에 느낌표를 붙이기보다, 선언할 때 옵셔널의 타입 뒤에 느낌표를 붙이십시오. 

암시적으로 언래핑된 옵셔널은 옵셔널이 처음 선언된 직후에 옵셔널의 값이 존재하는 것이 확인되고, 그 후 모든 지점에서 존재한다고 명확하게 추측할 수 있을 때 유용합니다. [Unowned References and Implicitly Unwrapped Optional Properties](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html#ID55)에서 설명하는 것처럼, 스위프트에서 암시적으로 언래핑된 옵셔널을 가장 중요하게 사용하는 것은 클래스의 초기화 동안입니다.

암시적으로 언래핑된 옵셔널은 내부적으로는 평범한 옵셔널이지만, 그것에 접근할 때마다 옵셔널 값을 언래핑할 필요가 없는 비-옵셔널 값처럼도 사용됩니다. 다음의 예시는 그들의 래핑된 값에 명시적인 `String`으로 접근할 때, 옵셔널 스트링과 암시적으로 언래핑된 옵셔널 스트링 간의 행동의 차이점을 보여줍니다:

```swift
let possibleString: String? = "An optional string."
let forcedString: String = possibleString! // 느낌표가 필요합니다

let assumedString: String! = "An implicitly unwrapped optional string."
let implicitString: String = assumedString // 느낌표가 필요하지 않습니다
```

암시적으로 언래핑된 옵셔널은 필요하다면 옵셔널을 강제 언래핑 시킬 수 있는 권한을 부여받은 것이라고 생각할 수 있습니다. 암시적으로 언래핑된 옵셔널 값을 사용할 때, 스위프트는 처음에는 그것을 평범한 옵셔널 값처럼 사용하려고 시도합니다; 만약 옵셔널처럼 사용할 수 없다면, 스위프트는 값을 강제 언래핑 시킵니다. 위의 코드에서, `implicitString`은 명백하고, 비-옵셔널인 `String` 타입을 가지고 있기 때문에, 옵셔널 값 `assumedString`은 그것의 값을 `implicitString`에 할당하기 전에 강제 언래핑 됩니다. 아래의 코드에서, `optionalString`은 명백한 타입을 가지고 있지 않기 때문에 이것은 평범한 옵셔널입니다.

```swift
let optionalString = assumedString
// optionalString의 타입은 "String?" 이고 assumedString은 강제 언래핑되지 않습니다.
```

만약 암시적으로 언래핑된 옵셔널이 `nil`이고 그것의 래핑된 값에 접근하려고 시도한다면, 런타임 오류를 일으킬 것입니다. 그 결과는 값을 가지고 있지 않은 평범한 옵셔널 뒤에 느낌표를 붙였을 때와 정확히 동일합니다. 

평범한 옵셔널을 확인하는 것과 같은 방법으로 암시적으로 언래핑된 옵셔널이 `nil`인지 아닌지 확인할 수 있습니다:

```swift
if assumedString != nil {
    print(assumedString!)
}
// "An implicitly unwrapped optional string." 출력
```

또한, 암시적으로 언래핑된 옵셔널을 옵셔널 바인딩과 함께 사용하여 단일 구문 안에서 그것의 값을 확인하고 언래핑 할 수 있습니다:

```swift
if let definiteString = assumedString {
    print(definiteString)
}
// "An implicitly unwrapped optional string." 출력
```

> 노트
>
> 변수가 이후에 `nil`이 될 가능성이 있는 경우에는 암시적으로 언래핑된 옵셔널을 사용하지 마십시오. 변수의 생명주기 동안 `nil` 값을 확인할 필요가 있다면 항상 평범한 옵셔널 타입을 사용하십시오. 

---

_* cope : 대처하다_</br>
_* exclamation point : 느낌표_</br>
_* branch : 분기_</br>
_* manipulate : 조종하다, 다루다, 처리하다_</br>

---

</details>

---

</details>
