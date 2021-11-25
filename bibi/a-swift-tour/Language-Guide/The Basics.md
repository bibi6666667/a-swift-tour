# The Basics

>  https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html

> Swift is a new programming language for iOS, macOS, watchOS, and tvOS app development. Nonetheless, many parts of Swift will be familiar from your experience of developing in C and Objective-C.
>
> Swift provides its own versions of all fundamental C and Objective-C types, including `Int` for integers, `Double` and `Float` for floating-point values, `Bool` for Boolean values, and `String` for textual data. Swift also provides powerful versions of the three primary collection types, `Array`, `Set`, and `Dictionary`, as described in [Collection Types](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html).
>
> Like C, Swift uses variables to store and refer to values by an identifying name. Swift also makes extensive use of variables whose values can’t be changed. These are known as constants, and are much more powerful than constants in C. Constants are used throughout Swift to make code safer and clearer in intent when you work with values that don’t need to change.
>
> In addition to familiar types, Swift introduces advanced types not found in Objective-C, such as tuples. Tuples enable you to create and pass around groupings of values. You can use a tuple to return multiple values from a function as a single compound value.
>
> Swift also introduces optional types, which handle the absence of a value. Optionals say either “there *is* a value, and it equals *x*” or “there *isn’t* a value at all”. Using optionals is similar to using `nil` with pointers in Objective-C, but they work for any type, not just classes. Not only are optionals safer and more expressive than `nil` pointers in Objective-C, they’re at the heart of many of Swift’s most powerful features.
>
> Swift is a *type-safe* language, which means the language helps you to be clear about the types of values your code can work with. If part of your code requires a `String`, type safety prevents you from passing it an `Int` by mistake. Likewise, type safety prevents you from accidentally passing an optional `String` to a piece of code that requires a non-optional `String`. Type safety helps you catch and fix errors as early as possible in the development process.



스위프트는 iOS, macOS, watchOS, tvOS 애플리케이션 개발을 위한 새로운 프로그래밍 언어입니다. 그렇긴 하지만, 스위프트의 많은 부분들은 C나 Objective-C 개발 경험으로부터 익숙할 것입니다.

스위프트는 C 와 Objective-C의 핵심적인 타입을 고유의 버전으로 제공합니다. 이는 정수 값을 위해 `Int`를 , 부동소수점 값을 위해 `Double`과 `Float`를, 불리언 값을 위해 `Bool`을, 텍스트 데이터를 위해 `String`을 제공하는 것을 포함합니다. 스위프트는 또한 Collection Types에 서술된 것과 같이, 세 가지 주요 컬렉션 타입인 Array, Set, Dictionary의 강력한 버전을 제공합니다.

C와 같이, 스위프트도 값을 저장하고 참조하기 위해 이름을 식별함으로써 변수를 사용합니다. 또한 스위프트는 값이 바뀔 수 없는 변수를 광범위하게 사용합니다. 이것은 상수라고도 알려져 있으며, C의 상수보다 훨씬 더 강력합니다. 상수는 당신이 변할 필요가 없는 값을 다룬다는 의도로 코드를 더 안전하고 명확하게 만들기 위해 스위프트 전체에 걸쳐 사용됩니다.

친숙한 타입들에 더해, 스위프트는 튜플과 같이 Objective-C에서는 찾을 수 없는 발전된 타입들을 소개합니다. 튜플은 값을 묶어서 만들고 전달하는 것을 가능하게 합니다. 당신은 함수로부터 여러 값들을 반환하기 위해 하나의 복합적인 값으로서 튜플을 사용할 수 있습니다.

스위프트는 또한 값의 없음을 다루는 옵셔널 타입을 소개합니다. 옵셔널은 "값이 있고, 그것은 x와 같다" 또는 "값이 전혀 없다"를 의미합니다. 옵셔널을 사용하는 것은 Objective-C에서 nil을 포인터와 함께 사용하는 것과 비슷하지만, 옵셔널은 클래스 뿐 아니라 어느 타입에나 사용할 수 있습니다. 옵셔널은 Objective-C의 nil포인터보다 더 안전하고 표현적일 뿐만 아니라, 스위프트의 많은 강력한 특성들의 핵심입니다.

스위프트는 타입-안전(type-safe) 언어입니다. 이는 당신이 코드로 다루는 값의 타입이 명확하도록 언어가 돕는다는 것을 의미합니다. 만약 당신의 코드의 일부가 String을 요구한다면, 실수로 Int를 전달하지 않도록 타입 안전성(type-safety)이 막아 줄 것입니다. 마찬가지로, 타입 안전성은 String을 요구하는 코드에 우연히 옵셔널 String을 전달하는 것을 막아줍니다. 타입 안전성은 개발 프로세스에서 가능한 빠른 시점에 에러를 찾아내고 수정하는 것을 도와줍니다.



## 단어 정리

- nonetheless 그렇긴 하지만.
- fundamental 근본적인. 핵심적인. / 기본 원칙. 핵심
- textual 원문의. (컴) 텍스트의?
- extensive 광범위한
- compound 복합적인 / 복합체
- absence 부재. 없음.
- identify 식별하다
- throughout ~내내. 처음부터 끝까지.
- intent 몰두하는. 꾀하는. 전념하는 / 의도
  - in intent
- type safety 타입 안전성

