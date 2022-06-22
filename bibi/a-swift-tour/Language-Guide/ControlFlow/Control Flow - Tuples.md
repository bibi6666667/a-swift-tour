# Control Flow - Tuples



## 튜플

여러 개의 값을 같은 switch문 내에서 테스트하기 위해 튜플을 사용할 수 있습니다. 튜플의 각 원소는 다른 값 또는 값의 범위에 대해 테스트될 수 있습니다. 와일드카드 패턴이라고 알려진 밑줄 문자(`_`)를 대신 사용하여, 가능한 어떤 값에도 맞출 수 있습니다.

아래 예시는 간단한 (Int, Int) 튜플 타입으로 표현된 ](x, y) 좌표를 받고, 예시와 같이 그래프 위에 분류합니다.

``` swift
let somePoint = (1, 1)
switch somePoint {
case (0, 0):
    print("\(somePoint)는 원점에 있습니다.")
case (_, 0):
    print("\(somePoint)는 x축에 있습니다")
case (0, _):
    print("\(somePoint)는 y축에 있습니다")
case (-2...2, -2...2):
    print("\(somePoint)는 상자 안에 있습니다")
default:
    print("\(somePoint)는 상자 밖에 있습니다")
}
// Prints "(1, 1) is inside the box"
```

이 switch문은 좌표가 (0, 0)원점에 있는지, 빨간색 x축 위에 있는지, 초록색 y축 위에 있는지, 원점을 중심으로 하는 4x4 상자 안에 있는지, 상자 밖에 있는지를 판단합니다.

C언어와 달리, 스위프트는 여러 개의 switch case들이 같은 값 또는 값들을 비교하는 것을 허용합니다. 사실, (0, 0)좌표는 이 예시의 모든 *네* case에 맞습니다. 하지만, 다중 비교가 가능하다면, 첫 번째 일치 case가 항상 사용됩니다. (0, 0)좌표는 `case(0, 0)`에 가장 먼저 일치하기 때문에, 다른 모든 일치 케이스들은 무시됩니다.



---

## 단어 정리

- interval 간격
- underscore 밑줄
  - underscore character 밑줄 문자 `_`
- axis 중심선. 축.
- 4-by-4 4x4
- allow A to B : A가 B하도록 허용하다

---

## 원문

#### Tuples

You can use tuples to test multiple values in the same `switch` statement. Each element of the tuple can be tested against a different value or interval of values. Alternatively, use the underscore character (`_`), also known as the wildcard pattern, to match any possible value.

The example below takes an (x, y) point, expressed as a simple tuple of type `(Int, Int)`, and categorizes it on the graph that follows the example.

``` swift
let somePoint = (1, 1)
switch somePoint {
case (0, 0):
    print("\(somePoint) is at the origin")
case (_, 0):
    print("\(somePoint) is on the x-axis")
case (0, _):
    print("\(somePoint) is on the y-axis")
case (-2...2, -2...2):
    print("\(somePoint) is inside the box")
default:
    print("\(somePoint) is outside of the box")
}
// Prints "(1, 1) is inside the box"
```

![../_images/coordinateGraphSimple_2x.png](https://docs.swift.org/swift-book/_images/coordinateGraphSimple_2x.png)

The `switch` statement determines whether the point is at the origin (0, 0), on the red x-axis, on the green y-axis, inside the blue 4-by-4 box centered on the origin, or outside of the box.

Unlike C, Swift allows multiple `switch` cases to consider the same value or values. In fact, the point (0, 0) could match all *four* of the cases in this example. However, if multiple matches are possible, the first matching case is always used. The point (0, 0) would match `case (0, 0)` first, and so all other matching cases would be ignored.