# The Basics - Optionals(4)

### Implicitly Unwrapped Optionals

As described above, optionals indicate that a constant or variable is allowed to have “no value”. Optionals can be checked with an `if` statement to see if a value exists, and can be conditionally unwrapped with optional binding to access the optional’s value if it does exist.

Sometimes it’s clear from a program’s structure that an optional will *always* have a value, after that value is first set. In these cases, it’s useful to remove the need to check and unwrap the optional’s value every time it’s accessed, because it can be safely assumed to have a value all of the time.

These kinds of optionals are defined as *implicitly unwrapped optionals*. You write an implicitly unwrapped optional by placing an exclamation point (`String!`) rather than a question mark (`String?`) after the type that you want to make optional. Rather than placing an exclamation point after the optional’s name when you use it, you place an exclamation point after the optional’s type when you declare it.

Implicitly unwrapped optionals are useful when an optional’s value is confirmed to exist immediately after the optional is first defined and can definitely be assumed to exist at every point thereafter. The primary use of implicitly unwrapped optionals in Swift is during class initialization, as described in [Unowned References and Implicitly Unwrapped Optional Properties](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html#ID55).

An implicitly unwrapped optional is a normal optional behind the scenes, but can also be used like a non-optional value, without the need to unwrap the optional value each time it’s accessed. The following example shows the difference in behavior between an optional string and an implicitly unwrapped optional string when accessing their wrapped value as an explicit `String`:

``` swift
let possibleString: String? = "An optional string."
let forcedString: String = possibleString! // requires an exclamation point

let assumedString: String! = "An implicitly unwrapped optional string."
let implicitString: String = assumedString // no need for an exclamation point
```

You can think of an implicitly unwrapped optional as giving permission for the optional to be force-unwrapped if needed. When you use an implicitly unwrapped optional value, Swift first tries to use it as an ordinary optional value; if it can’t be used as an optional, Swift force-unwraps the value. In the code above, the optional value `assumedString` is force-unwrapped before assigning its value to `implicitString` because `implicitString` has an explicit, non-optional type of `String`. In code below, `optionalString` doesn’t have an explicit type so it’s an ordinary optional.

``` swift
let optionalString = assumedString
// The type of optionalString is "String?" and assumedString isn't force-unwrapped.
```

If an implicitly unwrapped optional is `nil` and you try to access its wrapped value, you’ll trigger a runtime error. The result is exactly the same as if you place an exclamation point after a normal optional that doesn’t contain a value.

You can check whether an implicitly unwrapped optional is `nil` the same way you check a normal optional:

``` swift
if assumedString != nil {
    print(assumedString!)
}
// Prints "An implicitly unwrapped optional string."
```

You can also use an implicitly unwrapped optional with optional binding, to check and unwrap its value in a single statement:

``` swift
if let definiteString = assumedString {
    print(definiteString)
}
// Prints "An implicitly unwrapped optional string."
```

> NOTE
>
> Don’t use an implicitly unwrapped optional when there’s a possibility of a variable becoming `nil` at a later point. Always use a normal optional type if you need to check for a `nil` value during the lifetime of a variable.



---



## Implicitly Unwrapped Optionals

암시적 추출 옵셔널

위에 설명되었듯이, 옵셔널은 상수나 변수가 "값이 없음"을 갖도록 허용되었음을 의미합니다. 옵셔널은 if문을 통해 값이 있는지 확인하기 위해 확인될 수 있으며, 옵셔널 바인딩을 통해 조건부로 옵셔널의 값이 있으면 접근하도록 할 수 있습니다.

프로그램의 구조로부터, 종종 값이 처음 설정된 이후에 옵셔널의 값이 항상 있을 것임이 분명할 때가 있습니다. 이런 경우에, 옵셔널에 접근할 때 마다 값을 확인하고 옵셔널의 값을 추출할 필요가 없을 수 있습니다. 왜냐하면 값이 항상 있을 것으로 안전하게 추정되기 때문입니다.

이런 종류의 옵셔널은 *암묵적 추출 옵셔널*이라고 정의됩니다. 암묵적 추출 옵셔널은 옵셔널로 만들고 싶은 타입 뒤에 물음표(`String?`) 대신 느낌표(`String!`)를 작성해 만들 수 있습니다. 옵셔널을 사용할 때 옵셔널 이름 뒤에 느낌표를 붙이기보다, 옵셔널의 타입을 선언할 때 느낌표를 사용할 수 있습니다.

암묵적 추출 옵셔널은 옵셔널의 값이 처음 정의된 직후 옵셔널의 값이 있음이 확실하고, 그 이후에도 항상 값이 있을 것임이 분명할 때 유용합니다. 스위프트에서 암묵적 추출 옵셔널의 주된 사용은 클래스 초기화이며, [Unowned References and Implicitly Unwrapped Optional Properties](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html#ID55)에 설명되어 있습니다.

암묵적 추출 옵셔널은 내부적으로 일반적인 옵셔널이지만, 값에 접근할 때마다 옵셔널 값을 추출할 필요 없이 옵셔널이 아닌 값처럼 사용될 수도 있습니다. 이어지는 예시는 명시적인 String으로서 추출된 값에 접근할 때, 옵셔널 String과 암묵적 추출 옵셔널 String의 동작 차이를 보여줍니다.

``` swift
let possibleString: String? = "An optional string."
let forcedString: String = possibleString! // 느낌표를 필요로 합니다

let assumedString: String! = "An implicitly unwrapped optional string."
let implicitString: String = assumedString // 느낌표를 필요로 하지 않습니다
```

당신은 암묵적 추출 옵셔널을 필요할 때 옵셔널에게 강제 추출되도록 허락하는 것이라고 생각할 수 있습니다. 당신이 암묵적 추출 옵셔널 값을 사용할 때, 스위프트는 먼저 그것을 일반적인 옵셔널 값으로 사용하려고 시도합니다; 만약 그것이 옵셔널 값으로 사용될 수 없다면, 스위프트는 그 값을 강제 추출합니다. 위의 코드에서, 옵셔널 값 `assumedString`은 그 값을 `implicitString`에 할당하기 전에 강제 추출되었습니다. 왜냐하면 `implicitString`이 명확히 옵셔널이 아닌 String 타입의 값이기 때문입니다. 아래 코드에서, `optionalString`은 명확한 타입을 갖지 않기 때문에 그것은 일반적인 옵셔널이 됩니다.

``` swift
let optionalString = assumedString
// optionalString의 타입은 "String?"이며 assumedString은 강제 추출되지 않습니다.
```

만약 암시적 추출 옵셔널이 nil이고 당신은 그 추출된 값에 접근하려 한다면, 그것은 런타임 에러를 일으킬 것입니다. 그 결과는 당신이 값이 없는 일반적인 옵셔널 뒤에 느낌표를 붙이는 것과 같습니다.

당신은 일반적인 옵셔널을 확인할 때와 똑같은 방법으로 암묵적 추출 옵셔널이 nil인지 아닌지 확인할 수 있습니다:

``` swift
if assumedString != nil {
    print(assumedString!)
}
// "An implicitly unwrapped optional string."를 출력합니다
```

당신은 또한 옵셔널 바인딩에 암묵적 추출 옵셔널을 사용할 수 있으며, 그 값을 확인하고 추출하는 것을 하나의 구문으로 할 수 있습니다:

``` swift
if let definiteString = assumedString {
    print(definiteString)
}
// "An implicitly unwrapped optional string."를 출력합니다
```

> 노트
>
> 변수가 나중에 nil이 될 가능성이 있을 때는 암묵적 추출 옵셔널을 사용하지 마십시오. 변수의 생애주기 동안 nil을 확인할 필요가 있을 때는 항상 일반적인 옵셔널 타입을 사용하십시오.





---

## 단어 정리

- exclamation point : 느낌표
- as if 마치 ...인 것처럼.