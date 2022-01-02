# Integers

*Integers* are whole numbers with no fractional component, such as `42` and `-23`

인티저는 전체 숫자이다. 분수 컴포넌트가 아닌 42와 -23같이



Integers are either *signed* (positive, zero, or negative) or *unsigned* (positive or zero).

인티저는 양제로 음 또는 양 제로이다.



Swift provides signed and unsigned integers in 8, 16, 32, and 64 bit forms. 

스위프트는 8, 16, 32 그리고 64피트 형태의  둘다 제공한다 



These integers follow a naming convention similar to C, in that an 8-bit unsigned integer is of type `UInt8`, and a 32-bit signed integer is of type `Int32`. 

이 인티저들은 시 네이밍 컨밴션을 따른다. 팔 비트 언사인 인티저는 키워드이며 32비트 인티저는 키워드이다.



Like all types in Swift, these integer types have capitalized names.

스위프트의 모든 타입과 같이 대문자 이름의 타입을 갖는다.



## Integer Bounds

You can access the minimum and maximum values of each integer type with its `min` and `max`properties:

각 인티저 타입의 키워드 프로퍼티를 통해서 최솟값과 최대값을 접근할 수 있다.



The values of these properties are of the appropriate-sized number type (such as `UInt8` in the example above) and can therefore be used in expressions alongside other values of the same type.

이 속성들의 값은 적당한 크기의 숫자 타입이다 그리고 동일한 유형의 다른 값과 함께 표현식에 사용할 수 있따.



## Int

In most cases, you don’t need to pick a specific size of integer to use in your code. 

대부분의 상황에서 인티저 사이즈를 명시적으로 선택할 필요는 없을것이다.



Swift provides an additional integer type, `Int`, which has the same size as the current platform’s native word size:

현재 플랫폼 워드사이즈와 같은 크기를 가진 키워드 인티저 타입을 제공한다 .



Unless you need to work with a specific size of integer, always use `Int` for integer values in your code. 

세부적인 사이즈의 인티저와 함께 일할 필요가 없다. 항상 키워드 인티저를 사용한다면.



This aids code consistency and interoperability. 

이것은 코드가 일관적이고 상호 운영성적인을 지원한다.



Even on 32-bit platforms, `Int` can store any value between `-2,147,483,648` and `2,147,483,647`, and is large enough for many integer ranges.

심지어 32빝크 플래폿에서 인티저는 키워드 사이를 저장할 수 있다. 그리고 많은 인티저 범위를 위해서 충분히 크다.



## UInt

Swift also provides an unsigned integer type, `UInt`, which has the same size as the current platform’s native word size:

스위프트는 키워드를 제공한다. 현재 플렛폼의 워드 사이즈와 동일하다.



Use `UInt` only when you specifically need an unsigned integer type with the same size as the platform’s native word size. 

유인티저를 명시적으로 플랫폼 워드사이즈와 동일한 사이즈의 언사인드 인티저 타입을 필요로할 때 사용하세요.



If this isn’t the case, `Int` is preferred, even when the values to be stored are known to be nonnegative. 

// 만약 해당하지 않는다면 인티저를 추천합니다. 심지어 알려진 양수로 저장됩니다. ???



A consistent use of `Int` for integer values aids code interoperability, avoids the need to convert between different number types, and matches integer type inference, as described in [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322).

???



fractional: 분수의

appropriate-sized: 적당한 크기

therefore: 그러므로

alongside: 나란히, 함께

aid: 지원

interoperability: 상호 운영성

preferred: 취하다, 우선권을주다. 선호하다