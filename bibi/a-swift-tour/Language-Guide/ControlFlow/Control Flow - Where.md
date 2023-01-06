# Control Flow - Where

## Where

switch case는 추가적인 조건을 확인하기 위해 where절을 사용할 수 있습니다.

아래의 예시는 (x, y) 좌표를 다음 그래프에 분류합니다:

``` swift
let yetAnotherPoint = (1, -1)
switch yetAnotherPoint {
case let (x, y) where x == y:
    print("(\(x), \(y))는 x == y인 선 위에 있습니다.")
case let (x, y) where x == -y:
    print("(\(x), \(y))는 x == -y인 선 위에 있습니다.")
case let (x, y):
    print("(\(x), \(y))는 어떤 임의의 점입니다.")
}
// "(1, -1)는 x == -y인 선 위에 있습니다."를 출력합니다.
```

![../_images/coordinateGraphComplex_2x.png](https://docs.swift.org/swift-book/_images/coordinateGraphComplex_2x.png)

이 switch문은 좌표가 `x == y`인 녹색 대각선상에 있는지, `x == -y`인 보라색 대각선상에 있는지, 혹은 둘 모두에 해당하지 않는지를 결정합니다. 

세 개의 switch case들은 두 튜플 값을 일시적으로  `yetAnotherPoint`로부터 가져오는 x와 y라는 placeholder 상수를 선언합니다. 이 상수들은 동적인 필터를 만들기 위해 where절의 일부로 사용됩니다. 이 switch case는 값에 대해 where절의 조건이 true일 때만 `point`의 현재 값에 해당한다고 판단합니다.

이전의 예시와 같이, 마지막 case는 모든 가능한 나머지 값에 해당하며, 따라서 `default` case는 switch문을 철저하게 만들기 위해 필요하지 않습니다.

---

## 원문

---



> A `switch` case can use a `where` clause to check for additional conditions.
>
> The example below categorizes an (x, y) point on the following graph:
>
> 1. let yetAnotherPoint = (1, -1)
> 2. switch yetAnotherPoint {
> 3. case let (x, y) where x == y:
> 4. ​    print("(\(x), \(y)) is on the line x == y")
> 5. case let (x, y) where x == -y:
> 6. ​    print("(\(x), \(y)) is on the line x == -y")
> 7. case let (x, y):
> 8. ​    print("(\(x), \(y)) is just some arbitrary point")
> 9. }
> 10. // Prints "(1, -1) is on the line x == -y"
>
> ![../_images/coordinateGraphComplex_2x.png](https://docs.swift.org/swift-book/_images/coordinateGraphComplex_2x.png)
>
> The `switch` statement determines whether the point is on the green diagonal line where `x == y`, on the purple diagonal line where `x == -y`, or neither.
>
> The three `switch` cases declare placeholder constants `x` and `y`, which temporarily take on the two tuple values from `yetAnotherPoint`. These constants are used as part of a `where` clause, to create a dynamic filter. The `switch` case matches the current value of `point` only if the `where` clause’s condition evaluates to `true` for that value.
>
> As in the previous example, the final case matches all possible remaining values, and so a `default` case isn’t needed to make the `switch` statement exhaustive.

---

- arbitrary 임의의.