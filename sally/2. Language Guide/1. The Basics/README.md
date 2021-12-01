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

#### Declaring Constants and Variables

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

#### Type Annotations

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

---

## 상수와 변수

상수와 변수는 이름(예: `maximumNumberOfLoginAttempts` 혹은 `welcomeMessage`)과 특정한 타입의 값(예: 숫자 `10` 이나 문자열 `"Hello"`) 을 서로 연관 지어줍니다. *상수*의 값은 한번 할당하면 변경할 수 없지만, *변수*의 값은 나중에 다른 값을 할당할 수 있습니다. 

#### 상수와 변수의 선언

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

#### 타입 어노테이션

상수나 변수를 선언할 때, *type annotation* 를 사용하여 그것들에 저장할 수 있는 종류의 값들을 명확하게 할 수 있습니다. 타입 어노테이션을 작성하려면 상수나 변수 이름 뒤에 콜론을 적고, 한칸 띄우고 사용하려는 타입의 이름을 적으십시오. 

이 예에서 타입 어노테이션은 `welcomeMessage` 라는 이름의 변수가 `String` 값을 저장할 수 있다는 것을 알려줍니다:

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

여러 개의 연관된 같은 타입 변수들을 한 줄에서 정의하려면, 콤마로 구분하고 마지막 변수 이름 뒤에 하나의 타입 어노테이션을 사용하십시오: 

```swift
var red, green, blue: Double
```

> 노트
>
> 실제로 타입 어노테이션을 작성해야할 필요가 있는 경우는 적습니다. 상수나 변수를 처음 정의할 때 초기값을 제공하면, [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322) 에서 설명하는 것 처럼, 스위프트가 거의 항상 그 타입을 추론할 수 있습니다. 위의 `welcomeMessage` 예에서는 초기값이 주어지지 않았기 때문에, `welcomeMessage` 변수의 타입은 초기값으로부터 추론하지 않고 타입 어노테이션으로 정해집니다. 

---

_* annotation : 주석_</br>

---

</details>