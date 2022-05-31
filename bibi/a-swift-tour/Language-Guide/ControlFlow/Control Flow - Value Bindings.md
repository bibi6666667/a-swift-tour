# Control Flow - Value Bindings



## 값 바인딩

switch는 case 내부에서 사용하기 위해 case에 맞는 값 또는 값들을 임시 상수 또는 변수로 이름지을 수 있습니다. 값이 case 내부의 임시 상수 또는 변수에 묶이기 때문에, 이를 값 바인딩(value binding)이라고 합니다. 

아래의 예시는 (Int, Int)타입의 튜플로 표현되는 (x, y) 좌표를 받아 그 아래의 그래프에 분류합니다.

``` swift
let anotherPoint = (2, 0)
switch anotherPoint {
case (let x, 0):
    print("x축 위에 있으며 x값은 \(x)입니다")
case (0, let y):
    print("y축 위에 있으며 x값은 \(y)입니다")
case let (x, y):
    print("(\(x), \(y))라는 다른 영역에 있습니다")
}
// "x축 위에 있으며 x값은 2입니다"를 출력합니다.
```

![../_images/coordinateGraphMedium_2x.png](https://docs.swift.org/swift-book/_images/coordinateGraphMedium_2x.png)

이 switch문은 좌표가 빨간색 x축 위에 있는지, 초록색 y축 위에 있는지, 아니면 어떤 축 위도 아닌 다른 곳에 있는지를 판단합니다.

세 개의 switch case는 x와 y라는 placeholder 상수를 선언해 `anotherPoint`로부터 하나 또는 두 개의 튜플 값을 일시적으로 가져옵니다. 첫 번째 case인 `case (let x, 0)`은 y값이 0인 모든 좌표가 해당되며, 좌표의 x값을 임시 상수 `x`에 할당합니다. 유사하게, 두 번째 case인 `case (0, let y)`는 x좌표가 0인 모든 좌표가 해당되며, 좌표의 y값을 임시 상수 `y`에 할당합니다.

임시 상수들이 선언된 후에는 case의 코드블럭 내에서 사용될 수 있습니다. 여기서는, 좌표의 분류를 출력하기 위해 사용되었습니다.

이 switch문은 `default` case가 없습니다. 마지막 case인 `case let (x, y)`는, 어떤 값에도 해당하는 두 placeholder상수의 튜플을 선언합니다. `anotherPoint`는 항상 두 값의 튜플이기 때문에, 이 case는 모든 가능한 남은 값에 해당하며, 따라서 switch문이 모든 경우를 다루게 하기 위해(exhaustive) default` case가 필요하지 않습니다.



---

## 원문

#### Value Bindings

A `switch` case can name the value or values it matches to temporary constants or variables, for use in the body of the case. This behavior is known as *value binding*, because the values are bound to temporary constants or variables within the case’s body.

The example below takes an (x, y) point, expressed as a tuple of type `(Int, Int)`, and categorizes it on the graph that follows:

``` swift
let anotherPoint = (2, 0)
switch anotherPoint {
case (let x, 0):
    print("on the x-axis with an x value of \(x)")
case (0, let y):
    print("on the y-axis with a y value of \(y)")
case let (x, y):
    print("somewhere else at (\(x), \(y))")
}
// Prints "on the x-axis with an x value of 2"
```

![../_images/coordinateGraphMedium_2x.png](https://docs.swift.org/swift-book/_images/coordinateGraphMedium_2x.png)

The `switch` statement determines whether the point is on the red x-axis, on the green y-axis, or elsewhere (on neither axis).

The three `switch` cases declare placeholder constants `x` and `y`, which temporarily take on one or both tuple values from `anotherPoint`. The first case, `case (let x, 0)`, matches any point with a `y` value of `0` and assigns the point’s `x` value to the temporary constant `x`. Similarly, the second case, `case (0, let y)`, matches any point with an `x` value of `0` and assigns the point’s `y` value to the temporary constant `y`.

After the temporary constants are declared, they can be used within the case’s code block. Here, they’re used to print the categorization of the point.

This `switch` statement doesn’t have a `default` case. The final case, `case let (x, y)`, declares a tuple of two placeholder constants that can match any value. Because `anotherPoint` is always a tuple of two values, this case matches all possible remaining values, and a `default` case isn’t needed to make the `switch` statement exhaustive.