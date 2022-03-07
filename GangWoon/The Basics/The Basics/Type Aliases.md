# Type Aliases

*Type aliases* define an alternative name for an existing type. 

타입 별칭은 기존 타입의 양자택일 이름을 정의한다.



You define type aliases with the `typealias` keyword.

해당 키워드를 사용해서 타입 별칭을 사용한다.



Type aliases are useful when you want to refer to an existing type by a name that’s contextually more appropriate, such as when working with data of a specific size from an external source:

타입 별칭은 기존의 타입이 다른 이름의 컨셉으로 더 자세하게 추론되기 원할때 유용하다, 예를 들어서 외부소스로 부터 명시적인 데이터를 작업할 때



Once you define a type alias, you can use the alias anywhere you might use the original name:

타입 별칭을 정의하면, 당신은 오리지널 이름을 사용할 수 있는 어디에서든 명칭을 사용할 수 있습니다.



Here, `AudioSample` is defined as an alias for `UInt16`. 

유인티저16의 명칭으로 오디오샘플이 정의됐다.



Because it’s an alias, the call to `AudioSample.min` actually calls `UInt16.min`, which provides an initial value of `0` for the `maxAmplitudeFound` variable.

왜냐하면 이 명칭은 오디오 민의 실직적 호출은 유인티지16민이고, 이것은 초기 값을 0의 제공한다 해당 변수에게



Aliases: 별칭

alternative: 양자택일

Once: ~ 하면