# The Basics - Semicolons, Integers
# Semicolons
Unlike many other languages, Swift doesn’t require you to write a semicolon (;) after each statement in your code, although you can do so if you wish. However, semicolons are required if you want to write multiple separate statements on a single line:
``` swift
let cat = "🐱"; print(cat)
// Prints "🐱"
```

# Integers
Integers are whole numbers with no fractional component, such as 42 and -23. Integers are either signed (positive, zero, or negative) or unsigned (positive or zero).
Swift provides signed and unsigned integers in 8, 16, 32, and 64 bit forms. These integers follow a naming convention similar to C, in that an 8-bit unsigned integer is of type UInt8, and a 32-bit signed integer is of type Int32. Like all types in Swift, these integer types have capitalized names.
## Integer Bounds
You can access the minimum and maximum values of each integer type with its min and max properties:
``` swift
let minValue = UInt8.min  // minValue is equal to 0, and is of type UInt8
let maxValue = UInt8.max  // maxValue is equal to 255, and is of type UInt8
```
The values of these properties are of the appropriate-sized number type (such as UInt8 in the example above) and can therefore be used in expressions alongside other values of the same type.

## Int
In most cases, you don’t need to pick a specific size of integer to use in your code. Swift provides an additional integer type, Int, which has the same size as the current platform’s native word size:
* On a 32-bit platform, Int is the same size as Int32.
* On a 64-bit platform, Int is the same size as Int64.
Unless you need to work with a specific size of integer, always use Int for integer values in your code. This aids code consistency and interoperability. Even on 32-bit platforms, Int can store any value between -2,147,483,648 and 2,147,483,647, and is large enough for many integer ranges.

## UInt
Swift also provides an unsigned integer type, UInt, which has the same size as the current platform’s native word size:
* On a 32-bit platform, UInt is the same size as UInt32.
* On a 64-bit platform, UInt is the same size as UInt64.
> NOTE  
> Use UInt only when you specifically need an unsigned integer type with the same size as the platform’s native word size. If this isn’t the case, Int is preferred, even when the values to be stored are known to be nonnegative. A consistent use of Int for integer values aids code interoperability, avoids the need to convert between different number types, and matches integer type inference, as described in  [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322) .  


- - - -

### Semicolons
세미콜론

많은 다른 언어들과 다르게, 스위프트는 원한다면 쓸 수 있음에도 불구하고 코드의 각 구문 끝에 세미콜론(`;`)을 쓰도록 요구하지 않습니다. 하지만, 만약 한 줄에 여러 개의 구문을 적고 싶다면 세미콜론이 요구됩니다.
``` swift
let cat = "🐱"; print(cat)
// "🐱"를 출력합니다.
```

### Integers
정수형

정수형은 `42`나 `-23`처럼 분수의 구성 요소가 없는 모든 숫자입니다. 정수형은 부호가 있거나(양수, 0 또는 음수) 또는 부호가 없습니다(양수 또는 0).

 스위프트는 8, 16, 32, 64 비트 형태로 부호가 있는 정수형과 부호가 없는 정수형을 제공합니다. 이러한 정수형은 8비트의 부호가 없는 정수형을 `UInt8`, 32비트의 부호가 있는 정수형을 `Int32`라고 한다는 점에서 C언어와 비슷한 네이밍 컨벤션을 따릅니다. 스위프트의 다른 모든 타입들처럼, 이러한 정수형 타입은 대문자로 시작하는 이름을 갖습니다.

#### Integer Bounds
정수 경계

`min`과 `max` 프로퍼티로 각 정수 타입의 최소값과 최대값에 접근할 수 있습니다 :
``` swift
let minValue = UInt8.min  // minValue는 0과 같으며, 타입은 UInt8입니다.
let maxValue = UInt8.max  // maxValue는 255와 같으며, 타입은 UInt8입니다.
```
이 프로퍼티들의 값은 적절한 크기의 숫자 값을 가지며(위 예시의 `UInt8`과 같이), 그렇기 때문에 같은 타입의 다른 값 표현에 나란히 사용될 수 있습니다.

#### Int

대부분의 경우에, 코드에서 특정한 크기의 정수형을 고를 필요가 없습니다. 스위프트는 추가적으로 `Int`라는 정수 타입을 제공하며, 이 타입은 현재 플랫폼의 기본 단어 크기와 같은 크기를 갖습니다 : 
- 32비트 플랫폼에서, `Int`는 `Int32`와 같은 크기를 갖습니다.
- 64비트 플랫폼에서, `Int`는 `Int64`와 같은 크기를 갖습니다.
특정한 크기의 정수로 작업할 필요가 없는 한, 정수 값을 위해 항상 `Int`를 코드에 사용하십시오. 이것은 코드 일관성과 상호 운용성을 돕습니다. 심지어 32비트 플랫폼에서도, `Int`는  `-2,147,483,648` 와 
`2,147,483,647`  사이의 어떤 값이든 담을 수 있으며, 많은 정수 범위에 대해 충분히 큽니다.

#### UInt

스위프트는 `UInt`라는 부호가 없는 정수 타입도 제공하며, 현재 플랫폼의 기본 단어 크기와 같은 크기를 갖습니다 :
- 32비트 플랫폼에서, `UInt`는 `UInt32`와 같은 크기를 갖습니다.
- 64비트 플랫폼에서, `UInt`는 `UInt64`와 같은 크기를 갖습니다.

> 노트  
> 오직 플랫폼의 기본 단어 크기와 같은 크기의 부호가 없는 정수 타입이 특별히 필요할 때만 `UInt`를 사용하십시오. 만약 그런 경우가 아니라면, `Int`가 선호되며, 심지어 저장되어야 할 값들이 음수가 될 수 없다고 알고 있는 경우에도 그러합니다.  [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322) 에 설명되어 있듯이, 정수 값에 대한 `Int`의 일관적인 사용은 코드 상호운용성을 돕고, 다른 숫자 타입끼리 변환할 필요가 없으며, 정수 타입 참조와도 맞습니다.  
- - - -
## 단어 정리
- fractional 부분의. (수학) 분수의.
- bound 경계
- component 구성 요소.
- alongside 옆에. 나란히.
- consistent 일관된. 한결같은.
- consistency 일관성. 한결같음.
- interoperability 상호 운용성
- unsigned 부호가 없는
- signed 부호가 있는
- nonnegative 음이 아닌. (=0 또는 0보다 큰)
- in that ...라는 점에서. ...이므로.
- capitalize 대문자로 시작하다
- appropriate 적절한
- native 기본의. 타고난. 원래의. 출생지의.
- aid 돕다.
- word 단어
- if this isn't the case 그렇지 않은 경우.