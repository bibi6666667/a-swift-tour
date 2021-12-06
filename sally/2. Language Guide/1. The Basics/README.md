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