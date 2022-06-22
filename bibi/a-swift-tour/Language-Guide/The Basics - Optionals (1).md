# The Basics - Optionals (1)

You use *optionals* in situations where a value may be absent. An optional represents two possibilities: Either there *is* a value, and you can unwrap the optional to access that value, or there *isn’t* a value at all.

>  NOTE
>
> The concept of optionals doesn’t exist in C or Objective-C. The nearest thing in Objective-C is the ability to return `nil` from a method that would otherwise return an object, with `nil` meaning “the absence of a valid object.” However, this only works for objects—it doesn’t work for structures, basic C types, or enumeration values. For these types, Objective-C methods typically return a special value (such as `NSNotFound`) to indicate the absence of a value. This approach assumes that the method’s caller knows there’s a special value to test against and remembers to check for it. Swift’s optionals let you indicate the absence of a value for *any type at all*, without the need for special constants.

Here’s an example of how optionals can be used to cope with the absence of a value. Swift’s `Int` type has an initializer which tries to convert a `String` value into an `Int` value. However, not every string can be converted into an integer. The string `"123"` can be converted into the numeric value `123`, but the string `"hello, world"` doesn’t have an obvious numeric value to convert to.

The example below uses the initializer to try to convert a `String` into an `Int`:

``` swift
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)
// convertedNumber is inferred to be of type "Int?", or "optional Int"
```

Because the initializer might fail, it returns an *optional* `Int`, rather than an `Int`. An optional `Int` is written as `Int?`, not `Int`. The question mark indicates that the value it contains is optional, meaning that it might contain *some* `Int` value, or it might contain *no value at all*. (It can’t contain anything else, such as a `Bool` value or a `String` value. It’s either an `Int`, or it’s nothing at all.)

### nil

You set an optional variable to a valueless state by assigning it the special value `nil`:

``` swift
var serverResponseCode: Int? = 404
// serverResponseCode contains an actual Int value of 404
serverResponseCode = nil
// serverResponseCode now contains no value
```

>  NOTE
>
> You can’t use `nil` with non-optional constants and variables. If a constant or variable in your code needs to work with the absence of a value under certain conditions, always declare it as an optional value of the appropriate type.

If you define an optional variable without providing a default value, the variable is automatically set to `nil` for you:

``` swift
var surveyAnswer: String?
// surveyAnswer is automatically set to nil
```

> NOTE
>
> Swift’s `nil` isn’t the same as `nil` in Objective-C. In Objective-C, `nil` is a pointer to a nonexistent object. In Swift, `nil` isn’t a pointer—it’s the absence of a value of a certain type. Optionals of *any* type can be set to `nil`, not just object types.

---

## Optionals

 옵셔널

값이 없을 수 있는 상황에서 *옵셔널*을 사용합니다. 옵셔널은 두 가지 가능성을 나타냅니다: 값이 있어서 그 값에 접근하기 위해 옵셔널을 언래핑할 수 있거나, 값이 전혀 없거나.

> 노트
>
> C나 Objective-C 에는 옵셔널의 개념이 존재하지 않습니다. Objective-C 에 존재하는 가장 비슷한 개념은 객체를 반환하는 메서드로부터 nil 을 반환할 수 있다는 것이며, 이때 nil의 의미는 "유효한 객체가 없음" 입니다. 하지만, 이것은 객체에 대해서만 동작합니다 - 구조체, 기본 C 타입, 열거형 값에는 동작하지 않습니다. 이러한 타입에 대해서는, Objective-C 메서드는 일반적으로 값의 부재를 나타내기 위한 특별한 값 (예를 들어 `NSNotFound`)을 반환합니다. 이 접근은 메서드의 호출자가 테스트 대상이 되는 특별한 값이 있음을 알고 있고, 그것을 확인하는 것을 기억하고 있음을 가정합니다. 스위프트의 옵셔널은 특별한 상수를 필요로 하지 않고, 당신이 *어떤 타입*의 값의 부재이든 나타낼 수 있게 해 줍니다.

여기 옵셔널이 어떻게 값의 부재에 대처하는 데에 사용될 수 있는지에 대한 예시가 있습니다. 스위프트의 Int 타입은 String 값을 Int 값으로 변환하려고 시도하는 이니셜라이저를 가지고 있습니다. 하지만, 모든 문자열이 정수형으로 변환될 수 있는 것은 아닙니다. 문자열 "123"은 숫자 값 123으로 변환될 수 있지만, 문자열 "hello, world"는 변환될 명확한 숫자 값을 가지고 있지 않습니다.

아래의 예시는 String 을 Int 로 변환하기 위해 이니셜라이저를 사용합니다: 

``` swift
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)
// convertedNumber는"Int?" 또는 "optional Int" 타입으로 추론됩니다.
```

이니셜라이저가 실패할 수 있기 때문에, 이것은 Int보다는 *옵셔널* Int 를 반환합니다. 옵셔널 Int 는 `Int`가 아닌 `Int?`로 작성합니다. 물음표는 그것이 담고 있는 값이 옵셔널임을 나타내며, 이는 그것이 *어떤* Int 값을 담고 있거나, 혹은 그것이 어떤 값도 가지고 있지 않음을 의미합니다. (그것은 Bool 값이나 String 값 같은 다른 어떤 값도 담을 수 없습니다. 그것은 Int 이거나 아무것도 아니거나 둘 중 하나입니다.)

### nil

특별한 값인 `nil` 을 할당함으로서 옵셔널 값을 값이 없는 상태로 설정할 수 있습니다:

``` swift
var serverResponseCode: Int? = 404
// serverResponseCode는 실제로 404라는 Int 값을 담고 있습니다
serverResponseCode = nil
// serverResponseCode는 이제 어떤 값도 담고 있지 않습니다
```

> 노트
>
> 옵셔널이 아닌 상수와 변수에는 nil 을 사용할 수 없습니다. 만약 당신의 코드의 상수나 변수가 특정 상황에서 값의 없음을 다뤄야 한다면, 항상 적절한 타입의 옵셔널 값으로 선언하십시오.

만약 당신이 기본 값을 제공하지 않고 옵셔널 변수를 정의한다면, 그 변수는 당신을 위해 자동적으로 nil 으로 설정됩니다:

``` swift
var surveyAnswer: String?
// surveyAnswer 는 자동적으로 nil로 설정됩니다.
```

> 노트
>
> 스위프트의 nil 은 Objective-C 의 nil과는 다릅니다. Objective-C에서는, nil 은 객체의 부재에 대한 포인터입니다. 스위프트에서는, nil 은 포인터가 아닙니다 - nil은 특정 타입의 값의 없음입니다. 객체 타입만이 아닌 어떤 타입의 옵셔널도 nil 로 설정될 수 있습니다.

---



## 단어 정리

- in situations where ... : ... 한 상황에서.
- typically 일반적으로. 전형적으로.
- assume 추정하다
- indicate 나타내다
- cope 대처하다
  -  cope with ... ... 대처하다