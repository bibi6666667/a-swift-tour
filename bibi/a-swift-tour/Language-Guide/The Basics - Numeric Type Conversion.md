# The Basics - Numeric Type Conversion
## Numeric Type Conversion
Use the Int type for all general-purpose integer constants and variables in your code, even if they’re known to be nonnegative. Using the default integer type in everyday situations means that integer constants and variables are immediately interoperable in your code and will match the inferred type for integer literal values.
Use other integer types only when they’re specifically needed for the task at hand, because of explicitly sized data from an external source, or for performance, memory usage, or other necessary optimization. Using explicitly sized types in these situations helps to catch any accidental value overflows and implicitly documents the nature of the data being used.
## Integer Conversion
The range of numbers that can be stored in an integer constant or variable is different for each numeric type. An Int8 constant or variable can store numbers between -128 and 127, whereas a UInt8 constant or variable can store numbers between 0 and 255. A number that won’t fit into a constant or variable of a sized integer type is reported as an error when your code is compiled:
``` swift
let cannotBeNegative: UInt8 = -1
// UInt8 can't store negative numbers, and so this will report an error
let tooBig: Int8 = Int8.max + 1
// Int8 can't store a number larger than its maximum value,
// and so this will also report an error
```
Because each numeric type can store a different range of values, you must opt in to numeric type conversion on a case-by-case basis. This opt-in approach prevents hidden conversion errors and helps make type conversion intentions explicit in your code.
To convert one specific number type to another, you initialize a new number of the desired type with the existing value. In the example below, the constant twoThousand is of type UInt16, whereas the constant one is of type UInt8. They can’t be added together directly, because they’re not of the same type. Instead, this example calls UInt16(one) to create a new UInt16 initialized with the value of one, and uses this value in place of the original:
``` swift 
let twoThousand: UInt16 = 2_000
let one: UInt8 = 1
let twoThousandAndOne = twoThousand + UInt16(one)
```
Because both sides of the addition are now of type UInt16, the addition is allowed. The output constant (twoThousandAndOne) is inferred to be of type UInt16, because it’s the sum of two UInt16 values.
SomeType(ofInitialValue) is the default way to call the initializer of a Swift type and pass in an initial value. Behind the scenes, UInt16 has an initializer that accepts a UInt8 value, and so this initializer is used to make a new UInt16 from an existing UInt8. You can’t pass in any type here, however—it has to be a type for which UInt16 provides an initializer. Extending existing types to provide initializers that accept new types (including your own type definitions) is covered in  [Extensions](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html) .
## Integer and Floating-Point Conversion
Conversions between integer and floating-point numeric types must be made explicit:
``` swift
let three = 3
let pointOneFourOneFiveNine = 0.14159
let pi = Double(three) + pointOneFourOneFiveNine
// pi equals 3.14159, and is inferred to be of type Double
```
Here, the value of the constant three is used to create a new value of type Double, so that both sides of the addition are of the same type. Without this conversion in place, the addition would not be allowed.
Floating-point to integer conversion must also be made explicit. An integer type can be initialized with a Double or Float value:
``` swift
let integerPi = Int(pi)
// integerPi equals 3, and is inferred to be of type Int
```
Floating-point values are always truncated when used to initialize a new integer value in this way. This means that 4.75 becomes 4, and -3.9 becomes -3.
> NOTE  
> The rules for combining numeric constants and variables are different from the rules for numeric literals. The literal value 3 can be added directly to the literal value 0.14159, because number literals don’t have an explicit type in and of themselves. Their type is inferred only at the point that they’re evaluated by the compiler.  

- - - -

## Numeric Type Conversion
숫자 타입 변환

코드에서 정수형의 상수와 변수에, 그것이 음수가 될 수 없다고 알려져 있다고 하더라도 다용도로 Int타입을 사용하십시오. 대부분의 상황에 기본적으로 정수 타입을 사용하는 것은 당신의 코드에서 정수형 상수와 변수가 즉시 상호운용적임을 의미하며, 정수형 리터럴 값에 대해 추론된 타입에도 맞을 것입니다.
오직 당면한 문제에 특별히 필요한 경우에만 다른 정수형 타입을 사용하십시오. 예를 들어 외부 출처의 명시적으로 크기가 정해진 데이터를 위해서나, 성능이나 메모리 사용을 위해서나, 다른 필요한 최적화를 위해서입니다. 이러한 상황에서 명시적으로 크기가 정해진 타입을 사용하는 것은 우연한 값 오버플로우를 포착하는 것을 돕고, 사용된 데이터의 특성을 암묵적으로 기록합니다.

### Integer Conversion
정수형 변환

정수형 상수나 변수에 저장될 수 있는 숫자의 범위는 각 숫자 타입마다 다릅니다. `Int8` 타입의 상수나 변수는 -128에서 127 사이의 숫자를 저장할 수 있는 반면, `UInt8` 타입의 상수나 변수는 0부터 500 사이의 숫자를 저장할 수 있습니다. 크기가 정해진 정수형 타입 상수나 변수에 맞지 않는 숫자는 코드가 컴파일될 때 에러로 보고됩니다 :
``` swift
let cannotBeNegative: UInt8 = -1
// UInt8는 음수를 저장할 수 없기 때문에, 이 구문은 에러를 보고할 것입니다.
let tooBig: Int8 = Int8.max + 1
// Int8은 자신의 최댓값보다 큰 숫자를 저장할 수 없습니다.
// 따라서 이 구문 또한 에러를 보고할 것입니다.
```
각 숫자 타입이 다른 범위의 값을 저장하기 떄문에, 경우에 따라 근거를 가지고 숫자 타입 변환을 택해야만 합니다. 이러한 사전동의식 접근은 숨겨진 변환 오류를 막고 타입 변환 의도가 코드에 명시적으로 드러나도록 돕습니다.
한 특정 숫자 타입을 다른 타입으로 변환하기 위해, 존재하는 값으로 원하는 타입의 새로운 숫자를 초기화합니다. 아래의 예시에서, 상수  `twoThousand`는 `UInt16` 타입인 반면, 상수  `one`은 `UInt8`타입입니다. 이들은 같은 타입이 아니기 때문에, 직접 더해질 수 없습니다. 대신, 이 예시는 `one`의 값으로 초기화된 새로운 `UInt16`을 만들기 위해  `UInt16(one)`을 호출하며, 그 값을 원본 대신 사용합니다 :
``` swift 
let twoThousand: UInt16 = 2_000
let one: UInt8 = 1
let twoThousandAndOne = twoThousand + UInt16(one)
```
이제 덧셈의 양쪽이 `UInt16`타입이기 때문에, 덧셈이 허용됩니다. 결과 상수(`twoThousandAndOne`)는 `UInt16`타입으로 추론되며, 그 이유는 그것이 두 `UInt16`값의 합이기 때문입니다.
`어떤타입(초기값)`은 스위프트 타입의 이니셜라이저를 호출하기 위한 기본적인 방법이며, 그 안에 초기값을 전달합니다. 이면에서, `UInt16`은 `UInt8`값을 받는 이니셜라이저를 가지고 있으며, 그렇기 때문에 이 이니셜라이저가 존재하는 `UInt8`로부터 새로운  `UInt16`을 만들기 위해 사용됩니다. 하지만 여기에 어떤 타입이든 넘길 수 있는 것은 아닙니다 - 그것은 `UInt16`이 이니셜라이저에서 제공하는 타입이어야 합니다. 새로운 타입(당신이 정의한 타입을 포함해서)을 수용하는 이니셜라이저를 제공하도록 기존 타입을 확장하는 방법은 [확장](https://docs.swift.org/swift-book/LanguageGuide/Extensions.html) 에서 다룹니다.

### Integer and Floating-Point Conversion
정수형 및 부동소수점형 변환

정수형과 부동소수점형 숫자 타입 간의 변환은 반드시 명시적으로 만들어져야 합니다 :
``` swift
let three = 3
let pointOneFourOneFiveNine = 0.14159
let pi = Double(three) + pointOneFourOneFiveNine
// pi는 3.14159와 같으며, Double 타입의 것으로 추론됩니다.
```
상수 `three`의 값이 `Double` 타입의 새로운 값을 만들기 위해 사용되었으며, 그 결과 덧셈의 양쪽이 같은 타입이 되었습니다. 이 변환이 제자리에 없다면, 이 덧셈은 허용되지 않을 것입니다.
부동소수점형에서 정수형으로의 변환 역시 반드시 명시적으로 만들어져야 합니다. 정수 타입은 `Double`이나  `Float` 값으로 초기화될 수 있습니다 :
``` swift
let integerPi = Int(pi)
// integerPi는 3과 같으며,Int타입의 것으로 추론됩니다.
```
부동소수점 값은 새로운 정수형의 값으로 초기화되어 사용될 때 항상 이런 식으로 잘라내어집니다. 이는 `4.75` 는 `4`가 되고, `-3.9`는 `-3`이 됨을 의미합니다.
> 노트  
> 숫자 상수와 변수를 결합하기 위한 규칙은 숫자 리터럴을 위한 규칙과는 다릅니다. 리터럴 값 3은 직접 리터럴 값 0.14159에 더해질 수 있습니다. 왜냐하면 숫자 릴터럴은 명시적인 타입이 그 자체로는 없기 때문입니다. 그것들의 타입은 오직 컴파일러에 의해 평가되는 시점에만 추론됩니다.   

- - - -

## 단어 정리
- general-purpose 다목적의. 다용도의.
- interoperable 상호운용적인
- at hand 가까이에. 당면한.
- opt 택하다
	- opt in ... : ...에 참여(동의)하기로 하다
	- opt-in 옵트인 / 사전동의 ?
- case-by-case 개별적인
- basis 근거. 이유.
- truncate 자르다. 짧게 하다.
- evaluate 평가하다
- document (동사) 기록하다
- in place of ... : ...를 대신해서.
- behind the scene : 무대 뒤에서. 이면에서.
- extend 확장하다
- cover *다루다.
- in place 제자리에(있는)
- be of 추상명사 : of 추상명사 = 형용사 로 해석
	- `pi equals 3.14159, and is inferred to be of type Double`  : pi는 3.14159와 같으며, Double타입의 것으로 추론됩니다.
- combine 결합하다
- in and of itself 그것 자체는