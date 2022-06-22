# The Basics - Type Aliases

## Type Aliases

*Type aliases* define an alternative name for an existing type. You define type aliases with the `typealias` keyword.

Type aliases are useful when you want to refer to an existing type by a name that’s contextually more appropriate, such as when working with data of a specific size from an external source:

``` swift
typealias AudioSample = UInt16
```

Once you define a type alias, you can use the alias anywhere you might use the original name:

``` swift
var maxAmplitudeFound = AudioSample.min
// maxAmplitudeFound is now 0
```

Here, `AudioSample` is defined as an alias for `UInt16`. Because it’s an alias, the call to `AudioSample.min` actually calls `UInt16.min`, which provides an initial value of `0` for the `maxAmplitudeFound` variable.



---



## Type Aliases

타입 별칭

타입 별칭은 존재하는 타입에 대한 대안적인 이름을 정의합니다. `typealias` 키워드로 타입 별칭을 정의할 수 있습니다.

타입 별칭은 외부 소스로부터의 특정 크기를 지닌 데이터를 다룰 때와 같이, 맥락적으로 더 적절한 이름으로 존재하는 타입을 나타내고 싶을 때 유용합니다 :

``` swift
typealias AudioSample = UInt16
```

타입 별칭을 한 번 지정하면, 원래 이름을 사용할 곳 어디서나 그 별칭을 사용할 수 있습니다 :

``` swift
var maxAmplitudeFound = AudioSample.min
// maxAmplitudeFound은 이제 0입니다.
```

여기 `AudioSample`이 `UInt16`의 별칭으로 정의되어 있습니다. 그 별칭 때문에, `AudioSample.min`에 대한 호출은 실제로 `UInt16.min`을 호출하며, `maxAmplitudeFound` 변수의 초기값에 `0`을 전달합니다.

---

## 단어 정리

- alias [에일리어스] 가명. 예명. 별칭. (부사) 일명 ..라고 불리는.

- contextually 맥락적으로

- refer to ... 나타내다

  

