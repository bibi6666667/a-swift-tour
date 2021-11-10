# A Swift Tour - Control Flow (2)

> Notice how `let` can be used in a pattern to assign the value that matched the pattern to a constant.
>
> After executing the code inside the switch case that matched, the program exits from the switch statement. Execution doesn’t continue to the next case, so you don’t need to explicitly break out of the switch at the end of each case’s code.
>
> You use `for`-`in` to iterate over items in a dictionary by providing a pair of names to use for each key-value pair. Dictionaries are an unordered collection, so their keys and values are iterated over in an arbitrary order.
>
> ```swift
> let interestingNumbers = [
>     "Prime": [2, 3, 5, 7, 11, 13],
>     "Fibonacci": [1, 1, 2, 3, 5, 8],
>     "Square": [1, 4, 9, 16, 25],
> ]
> var largest = 0
> for (_, numbers) in interestingNumbers {
>     for number in numbers {
>         if number > largest {
>             largest = number
>         }
>     }
> }
> print(largest)
> // Prints "25"
> ```
>
> > EXPERIMENT
> >
> > Replace the `_` with a variable name, and keep track of which kind of number was the largest.
>
> Use `while` to repeat a block of code until a condition changes. The condition of a loop can be at the end instead, ensuring that the loop is run at least once.
>
> ```swift
> var n = 2
> while n < 100 {
>     n *= 2
> }
> print(n)
> // Prints "128"
> 
> var m = 2
> repeat {
>     m *= 2
> } while m < 100
> print(m)
> // Prints "128"
> ```
>
> You can keep an index in a loop by using `..<` to make a range of indexes.
>
> ``` swift
> var total = 0
> for i in 0..<4 {
>     total += i
> }
> print(total)
> // Prints "6"
> ```
>
> Use `..<` to make a range that omits its upper value, and use `...` to make a range that includes both values.



## 제어 흐름 (2)

패턴에 맞는 값을 상수에 할당하기 위한 패턴에서 let이 어떻게 사용될 수 있는지에 대해 주목하십시오. (`case let x where x.hasSuffix("pepper"):`)

매치되는 switch의 case의 코드를 실행한 뒤에, 프로그램은 switch문을 빠져나옵니다. 실행은 다음 case로 계속되지 않으므로, switch의 case의 코드마다 매번 명시적으로 나갈(break를 쓸) 필요가 없습니다.

딕셔너리의 항목들을 반복하기 위해 각 키-값 쌍에 사용하기 위한 한 쌍의 이름들을 제공함으로써 for-in을 사용할 수 있습니다. 딕셔너리는 순서가 없는 컬렉션이므로, 그 키와 값들은 임의의 순서로 반복됩니다.

```swift
let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
]
var largest = 0
for (_, numbers) in interestingNumbers {
    for number in numbers {
        if number > largest {
            largest = number
        }
    }
}
print(largest)
// Prints "25"
```

> 실험
>
> _ 를 변수 이름으로 대체하고, 어떤 종류의 숫자가 가장 큰 숫자인지 계속 추적해 보세요.

조건이 변화할 때 까지 코드 블럭을 반복하기 위해 while을 사용해 보세요. 반복문의 조건은 맨 끝에 있을 수도 있으며, 그 반복문이 최소 한 번은 실행되게 합니다.

```swift
var n = 2
while n < 100 {
    n *= 2
}
print(n)
// Prints "128"

var m = 2
repeat {
    m *= 2
} while m < 100
print(m)
// Prints "128"
```

인덱스 범위를 만들기 위해 `..<`를 사용함으로써 반복문의 인덱스를 유지할 수 있습니다.

```swift
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
// Prints "6"
```

상위 값을 포함하지 않는 범위를 만들기 위해 `..<`를, 양쪽 값을 포함하는 범위를 만들기 위해 `...`를 사용하십시오.



## 영단어 정리

- excute 실행하다
- execution 실행
- iterate 반복하다
- arbitrary 임의의
  - arbitrary order 임의의 순서로
- omit 빠뜨리다
- intersection 교집합
- superset 상위집합
- subset 부분집합
- disjoint set 서로소 집합
- alphanumeric 영숫자 (영어 + 숫자)
- asign A to B

