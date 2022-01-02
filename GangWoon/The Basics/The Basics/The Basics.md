# The Basics

Swift is a new programming language for iOS, macOS, watchOS, and tvOS app development. 

스위프트는 세가지를 위한 앱 개발를 위한 새로운 프로그래밍 언어이다 



Nonetheless, many parts of Swift will be familiar from your experience of developing in C and Objective-C.

그럼에도 불구하고 스위프트의 많은 부분들은 씨와 옵젝씨로 개발한 경험과 매우 유사할겁니다.



Swift provides its own versions of all fundamental C and Objective-C types, including `Int` for integers, `Double` and `Float` for floating-point values, `Bool` for Boolean values, and `String` for textual data.

스위프트는 씨그리고 옵젝씨 타입의 모든 기초를 우리만의 버전으로 제공합니다. 인티저 더블 플로트, 불린 그리고 스트링



Swift also provides powerful versions of the three primary collection types, `Array`, `Set`, and `Dictionary`, as described in [Collection Types](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html).

스위프트는 또한 주 컬렉션 타입의 버전을 제공합니다. 배열 집합 그리고 딕 이것들은 컬랙션 타입들에 묘사되었습니다.



Like C, Swift uses variables to store and refer to values by an identifying name. 

씨와 같이 스위프트는 변수를 저장하기 위해 사용하고 식별가능한 이름으로 값을 추론합니다.



Swift also makes extensive use of variables whose values can’t be changed. 

스위프트는 변할 수 없는 값들을 광범위하게 사용할 수 있습니다.



These are known as constants, and are much more powerful than constants in C. 

상수로 알려져있습니다. 그리고 씨의 상수보다 더 파워풀합니다.



Constants are used throughout Swift to make code safer and clearer in intent when you work with values that don’t need to change.

상수는 스위프트 전체에 사용됩니다. 의도적으로 안전하고 깔끔하게 만들기 위해서그 값이 변경할 필요가 없을때

변경할 필요가 없는 값을 갖고 작업할 때 의도적으로 안전하고 깔금하게 만들기 위해 스위프트 전체에 상수를 사용합니다. ;; 엄청 어렵네요



In addition to familiar types, Swift introduces advanced types not found in Objective-C, such as tuples. 

게다가 친숙한 타입, 스위프트는 소개합니다 진화한 타입들 옵젝씨에서 볼수 없는 튜플과 같은



Tuples enable you to create and pass around groupings of values. 

튜플은 값들을 생성하고 패스할 수 있도록 한다.



You can use a tuple to return multiple values from a function as a single compound value.

당신은 튜플을 함수로 부터 다중 값을 단일 복합 값으로 리턴하도록 사용할 수 있다.



Swift also introduces optional types, which handle the absence of a value. 

스위프트는 또한 옵셔널 타입들을 제공한다. 그 값은 값의 결석에 대해서 다룬다.

스위프트는 또한 옵셔널 타입들을 제공한다. 그 값은 값의 부재에 대해서 다룬다.



Optionals say either “there *is* a value, and it equals *x*” or “there *isn’t* a value at all”. 

옵셔널은 "값이 있어 그리고 이건  x와 동일해"와 "거기엔 값이 없어"로 말할 수 있다.



Using optionals is similar to using `nil` with pointers in Objective-C, but they work for any type, not just classes. 

옵셔널을 사용하는건 옵젝씨에서 포인터의 닐을 사용하느것과 유사하다 하지만 어떤 타입과 사용가능하다 클래스에서만 가능하지 않고



Not only are optionals safer and more expressive than `nil` pointers in Objective-C, they’re at the heart of many of Swift’s most powerful features.

옵젝씨 포인터 닐보다 옵셔널이 안전하고 표현력있을 뿐만 아니라 스위프트의 강력한 기능의 핵심이다



Swift is a *type-safe* language, which means the language helps you to be clear about the types (of values your code can work with.

스위프트는 타입 안전 언어이다. 즉 언어가 당신을 도와준다 타입에 대해서 명확하도록  ???



If part of your code requires a `String`, type safety prevents you from passing it an `Int` by mistake. 

만약에 당신의 코드가 스트링을 요구한다면, 타입 안전은 실수로 인티저를 넘기는걸 방지할거다.



Likewise, type safety prevents you / from accidentally passing an optional `String` / to a piece of code that requires a non-optional `String`. 

유사하게 타입 안전은 논옵셔널 스트링을 요구하는 코드에게 실수로 옵셔널 스트링을 전달하는 것을 당신으로 부터 막습니다.



Type safety helps you catch and fix errors as early as possible in the development process.

타입 안전은 개발 과정에서 가능한 빨리 에러를 당신에게 잡거나 고칠 수 있도록 도와준다.



extensive: 광대한

in intent: 의도적으로

throughout: 전체에

compound: 복합

absence: 없음, 결석(알고 있던 뜻)

features: 기능