## Optionals

You use *optionals* in situations where a value may be absent. 

값이 없을 수도 있을 경우에 옵셔널을 사용하세요.



An optional represents two possibilities: Either there *is* a value, and you can unwrap the optional to access that value, or there *isn’t* a value at all.

옵셔널은 두가지 가능성에 대해서 나타냅니다. 하나는 값이며 당신이 값을 벗김으로써 접근할 수 있습니다. 또는 아무것도 없는 걸 의미합니다.



The concept of optionals doesn’t exist in C or Objective-C. 

옵셔널 컨셉은 씨나 오브젝트 씨에 존재하지 않습니다.



The nearest thing in Objective-C is the ability to return `nil` from a method that would otherwise return an object, with `nil` meaning “the absence of a valid object.” 

오브젝티브 씨에서 오브젝트를 리턴하는 메소드로부터 닐을 리턴하는 것이 가장 근접합니다. 닐의 뜻은 가능한 오브젝트의 부재를 뜻합니다.



However, this only works for objects—it doesn’t work for structures, basic C types, or enumeration values. 

그러나 이것은 오브젝트를 위해서만 작동합니다. 구조체 기존 씨타입 또는 열거형에선 작동하지 않습니다.



For these types, Objective-C methods typically return a special value (such as `NSNotFound`) to indicate the absence of a value. 

이 타입들을 위해서, 오브젝트 씨 메소드늘은 전형적으로 값의 결석을 표시하기 위해서 특별한 값을 리턴합니다(엔에스 낫 파운드와 같이)



This approach assumes that the method’s caller knows there’s a special value to test against and remembers to check for it. 

메소드 콜러가 특별한 값을 알고 있고, 이것을 위해 체크를 해야한다는 가정입니다.



Swift’s optionals let you indicate the absence of a value for *any type at all*, without the need for special constants.

스위프트의 옵셔널은 모든 타입을 위한 값의 부재를 나타나도록 시킨다.특별한 내용으 요구가 없이도



Here’s an example of how optionals can be used to cope with the absence of a value. 

여기에서 어떻게 옵셔널이 값의 부재를 덮어서 사용하는지 알 수 있습니다.



Swift’s `Int` type has an initializer which tries to convert a `String` value into an `Int` value. 

스위프트의 인트 타입 string을 인티저 값으로 변경할 수 있도록 시도하는 초기화가 있다.



However, not every string can be converted into an integer. 

하지만 모든 스트링이 인티저가 될 순 없다.



The string `"123"` can be converted into the numeric value `123`, but the string `"hello, world"` doesn’t have an obvious numeric value to convert to.

123 스트링이 123 숫자로 전환할 수 있지만, 안녕 세계를 명백하게 숫자로 변경할 순 없다.



The example below uses the initializer to try to convert a `String` into an `Int`:

스트링을 인티저로 변경하려고 시도하는 초기화는 아래 예시에서 볼 수 있다.



Because the initializer might fail, it returns an *optional* `Int`, rather than an `Int`. 

초기화가 만약 실패한다면 옵셔널 인트를 리턴할것이다 인티저 대신



An optional `Int` is written as `Int?`, not `Int`. 

옵셔널 인트는 위와같이 작성한다.



The question mark indicates that the value it contains is optional, meaning that it might contain *some* `Int` value, or it might contain *no value at all*. 

물음표는 옵셔널을 포함하고 있는걸 가리킨다, 인티저 값을 갖고 있거나 또는 아무것도 없는 걸 뜻한다.



(It can’t contain anything else, such as a `Bool` value or a `String` value. It’s either an `Int`, or it’s nothing at all.)

하지만 뭐든걸 갖는걸 뜻하는 건 아니다 불값이나 스트링 값같이. 이것 오로지 인티저나 아무것도 없는 걸 의미한다.



assumes: 가정하다

against: 반대하여

cope: 대처하다



