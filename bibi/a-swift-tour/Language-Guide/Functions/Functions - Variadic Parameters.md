# Functions - Variadic Parameters

> https://docs.swift.org/swift-book/LanguageGuide/Functions.html#:~:text=parameters%20are%20omitted.-,Variadic%20Parameters,-A%20variadic%20parameter

가변 파라미터

*가변* 파라미터는 0개 이상의 구체 타입의 값을 받을 수 있습니다. 가변 파라미터는 함수가 호출될 때 입력 값으로 여러 개를 전달받을 수 있음을 나타내기 위해 사용할 수 있습니다. 세 개의 마침표(`...`)를 파라미터의 타입 이름 뒤에 넣음으로써 가변 파라미터를 작성할 수 있습니다.

가변 파라미터로 전달된 값들은 함수의 body 내부에서 적절한 타입의 배열로 사용 가능합니다. 예를 들어, `numbers`라는 이름의 가변 파라미터가 `Double...`타입이라면, 함수의 body에서 `numbers`라는 이름의 `Double`타입 상수 배열로 사용 가능합니다.

아래의 예시는 모든 길이의 숫자 리스트들의 *산술 평균*(*평균*이라고도 알려진)을 계산합니다:

``` swift
func arithmeticMean(_ numbers: Double...) -> Double {
    var total: Double = 0
    for number in numbers {
        total += number
    }
    return total / Double(numbers.count)
}
arithmeticMean(1, 2, 3, 4, 5)
// 이 다섯 숫자들의 산술평균인 3.0을 반환합니다.
arithmeticMean(3, 8.25, 18.75)
// 이 세 숫자들의 산술평균인 10.0을 반환합니다.
```

함수는 여러 개의 가변 파라미터를 가질 수 있습니다. 가변 파라미터의 바로 뒤에 오는 첫 번째 파라미터는 반드시 아규먼트 레이블을 가져야 합니다. 아규먼트 레이블은 어떤 아규먼트가 가변 파라미터로 전달되었는지, 그리고 어떤 아규먼트가 가변 파라미터 다음의 파라미터로 전달되었는지를 모호하지 않게 해줍니다.





---

- period character 마침표 (.)
- arithmetic mean 산술 평균 (=평균)