# A Swift Tour - Simple Values (1)



> ## Simple Values
>
> Use `let` to make a constant and `var` to make a variable. The value of a constant doesn’t need to be known at compile time, but you must assign it a value exactly once. This means you can use constants to name a value that you determine once but use in many places.
>
> ```swift
> var myVariable = 42
> myVariable = 50
> let myConstant = 42
> ```
>
> A constant or variable must have the same type as the value you want to assign to it. However, you don’t always have to write the type explicitly. Providing a value when you create a constant or variable lets the compiler infer its type. In the example above, the compiler infers that `myVariable` is an integer because its initial value is an integer.
>
> If the initial value doesn’t provide enough information (or if isn’t an initial value), specify the type by writing it after the variable, separated by a colon.
>
> ```swift
> let implicitInteger = 70
> let implicitDouble = 70.0
> let explicitDouble: Double = 70
> ```
>
> > EXPERIMENT
> >
> > Create a constant with an explicit type of `Float` and a value of `4`.
>
> Values are never implicitly converted to another type. If you need to convert a value to a different type, explicitly make an instance of the desired type.
>
> ```swift
> let label = "The width is "
> let width = 94
> let widthLabel = label + String(width)
> ```
>
> >  EXPERIMENT
> >
> > Try removing the conversion to `String` from the last line. What error do you get?



## 단순한 값

상수를 만들기 위해 `let`을, 변수를 만들기 위해 `var`를 사용하십시오. 상수의 값은 컴파일 시점에 알려질 필요는 없지만, 반드시 단 한 번만 할당되어야 합니다. 이것은 당신이 한 번 결정하지만 여러 곳에서 사용할 값에 이름을 붙이기 위해 상수들을 사용할 수 있음을 의미합니다.

``` swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```

상수 또는 변수는 당신이 그것에 할당하기를 원하는 값과 반드시 같은 타입을 가져야 합니다. 하지만, 항상 타입을 명시적으로 작성해야 하는 것은 아닙니다. 상수나 변수를 만들 때 값을 제공하는 것은 컴파일러가 그것의 타입을 추론하도록 해 줍니다. 위의 예시에서, 컴파일러는 `myVariable`가 정수형임을 추론하는데, 이는 그것의 초기값이 정수이기 때문입니다.

만약 초기값이 충분한 정보를 제공하지 않는다면 (또는 그것이 초기값이 아니라면), 콜론으로 구분된 타입을 변수 뒤에 적어 구체화하십시오.

```swift
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
```

> 실험
>
> 명시적 타입이 Float이고 값이 4인 상수를 만들어 보십시오.
>
> `let explicitFloat: Float = 4`

값은 절대로 암묵적으로 다른 타입으로 변환되지 않습니다. 만약 값을 다른 타입으로 변환해야 한다면, 명시적으로 원하는 타입의 인스턴스를 만드십시오.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

> 실험
>
> 마지막 줄에서 String으로의 변환을 지워 보십시오. 어떤 에러를 마주하게 됩니까?
>
> `error: binary operator '+' cannot be applied to operands of type 'String' and 'Int'`



## 영단어 정리

- constant 상수
- variable 변수
- determine 결정하다
- explicitly 분명하게. 명시적으로.
- implicitly 암묵적으로.
- desired 원했던
- convert 변환되다 / 변환시키다
- conversion 변환
- Create a constant with an explicit type of `Float` and a value of `4`.
  - type of , value of ?
- binary 2진법의, 이항의
- operator (컴) 연산자
- operand (컴) 피연산자

