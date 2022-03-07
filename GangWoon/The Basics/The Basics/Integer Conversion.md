# Integer Conversion
The range of numbers that can be stored in an integer constant or variable is different for each numeric type. 
정수 상수 또는 변수는 저장할 수 있는 숫자의 범위가 숫자 유형마다 다르다

An Int8 constant or variable can store numbers between -128 and 127, whereas a UInt8 constant or variable can store numbers between 0 and 255. 
인트8 상수 또는 변수는 마이너스 128부터 127 사이의 수를 저장할 수 있는 반면 유인티저8 상수 또는 변수는 0부터 255까지 저장할 수 있다.

A number that won’t fit into a constant or variable of a sized integer type is reported as an error when your code is compiled:
?? 헬프으으 문장을 어떻게 나눌지 모르겠습니다.

Because each numeric type can store a different range of values, you must opt in to numeric type conversion on a case-by-case basis. 
각각의 숫자 타입은 다른 범위 값을 저장할 수 있기 때문에 당신은 사례별로 숫자 타입 변환을 골라야만한다.

This opt-in approach prevents hidden conversion errors and helps make type conversion intentions explicit in your code.
이 옵트인 접근법은 숨겨진 변환 에러 예방하고 그리고 타입 변환 의도를 명시적으로 만들도록 도와준다.

To convert one specific number type to another, you initialize a new number of the desired type with the existing value. 
명시된 숫자 타입을 다른 타입으로 변환하기 위해서 당신은 기존 값으로 원하는 유형의 새 숫자를 초기화해야한다.

In the example below, the constant twoThousand is of type UInt16, whereas the constant one is of type UInt8. 
아래 예시에서 그 상수의 타입은 유인티저16인 반면에 그 상수 중 하나의 타입은 유인티저8이다

They can’t be added together directly, because they’re not of the same type. 
그들은 직접 더할 수 없다 왜냐하면 같은 타입이 아니기 때문이다.

Instead, this example calls UInt16(one) to create a new UInt16 initialized with the value of one, and uses this value in place of the original:
대신에 예시에서 유인티저 원을 호출해서 새로운 유인티저를 초기화했다 그리고 원본대신 해당 값을 사용했다.

Because both sides of the addition are now of type UInt16, the addition is allowed. 
더하기의 양쪽 타입이 유인티저16임으로 덧셈이 허락되어진다.

The output constant (twoThousandAndOne) is inferred to be of type UInt16, because it’s the sum of two UInt16 values.
결과물은 유인티저 타입으로 추론된다. 왜냐면 유인티저 값의 합이기 때문이다.

SomeType(ofInitialValue) is the default way to call the initializer of a Swift type and pass in an initial value. 
SomeType(ofInitialValue)은 스위프트 유형의 초기화를 호출하고 초기 값을 전달하는 기본 방법이다.

Behind the scenes, UInt16 has an initializer that accepts a UInt8 value, and so this initializer is used to make a new UInt16 from an existing UInt8. 
UInt16에는 UInt8을 사용해서 초기화할 수 있음으로 8을 사용해서 16을 새롭게 만들 수 있다.

You can’t pass in _any_ type here, however—it has to be a type for which UInt16 provides an initializer. 
당신은 어떤 타입이든 전달할 순 없다 그러나 유인터 초기화ㅣ에서 제공되는 타입이여야합니다.

Extending existing types to provide initializers that accept new types (including your own type definitions) is covered in  [Extensions](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html) .
새로운 유형을 허용하는 초기화를 제공하기 위해 기존 유형을 확장하는 건 확장에서 다뤄진다.

numeric: 숫자
opt: 고르다
on a case-by-case basis: 사례별로
**옵트인(Opt-in)**은 당사자가 개인  [데이터](https://ko.wikipedia.org/wiki/%EB%8D%B0%EC%9D%B4%ED%84%B0)  수집을 허용하기 전 까지 당사자의 데이터 수집을 금지하는 제도이다.
intentions: 의도
conversion: 변환