# A Swift Tour - Functions and Closures

> ## Functions and Closures
>
> Use `func` to declare a function. Call a function by following its name with a list of arguments in parentheses. Use `->` to separate the parameter names and types from the function’s return type.
>
> ```swift
> func greet(person: String, day: String) -> String {
>        return "Hello \(person), today is \(day)."
> }
> greet(person: "Bob", day: "Tuesday")
> ```
>
> > EXPERIMENT
> >
> > Remove the `day` parameter. Add a parameter to include today’s lunch special in the greeting.
>
> By default, functions use their parameter names as labels for their arguments. Write a custom argument label before the parameter name, or write `_` to use no argument label.
>
> ``` swift
> func greet(_ person: String, on day: String) -> String {
>     return "Hello \(person), today is \(day)."
> }
> greet("John", on: "Wednesday")
> ```
>
> Use a tuple to make a compound value—for example, to return multiple values from a function. The elements of a tuple can be referred to either by name or by number.
>
> ```swift
> func calculateStatistics(scores: [Int]) -> (min: Int, max: Int, sum: Int) {
>     var min = scores[0]
>     var max = scores[0]
>     var sum = 0
> 
>     for score in scores {
>         if score > max {
>             max = score
>         } else if score < min {
>             min = score
>         }
>         sum += score
>     }
> 
>     return (min, max, sum)
> }
> let statistics = calculateStatistics(scores: [5, 3, 100, 3, 9])
> print(statistics.sum)
> // Prints "120"
> print(statistics.2)
> // Prints "120"
> ```
>
> Functions can be nested. Nested functions have access to variables that were declared in the outer function. You can use nested functions to organize the code in a function that’s long or complex.
>
> ```swift
> func returnFifteen() -> Int {
>     var y = 10
>     func add() {
>         y += 5
>     }
>     add()
>     return y
> }
> returnFifteen()
> ```
>
> Functions are a first-class type. This means that a function can return another function as its value.
>
> ```swift
> func makeIncrementer() -> ((Int) -> Int) {
>     func addOne(number: Int) -> Int {
>         return 1 + number
>     }
>     return addOne
> }
> var increment = makeIncrementer()
> increment(7)
> ```
>
> A function can take another function as one of its arguments.
>
> ```swift
> func hasAnyMatches(list: [Int], condition: (Int) -> Bool) -> Bool {
>     for item in list {
>         if condition(item) {
>             return true
>         }
>     }
>     return false
> }
> func lessThanTen(number: Int) -> Bool {
>     return number < 10
> }
> var numbers = [20, 19, 7, 12]
> hasAnyMatches(list: numbers, condition: lessThanTen)
> ```
>
> Functions are actually a special case of closures: blocks of code that can be called later. The code in a closure has access to things like variables and functions that were available in the scope where the closure was created, even if the closure is in a different scope when it’s executed—you saw an example of this already with nested functions. You can write a closure without a name by surrounding code with braces (`{}`). Use `in` to separate the arguments and return type from the body.
>
> ```swift
> numbers.map({ (number: Int) -> Int in
>     let result = 3 * number
>     return result
> })
> ```
>
> > EXPERIMENT
> >
> > Rewrite the closure to return zero for all odd numbers.
>
> You have several options for writing closures more concisely. When a closure’s type is already known, such as the callback for a delegate, you can omit the type of its parameters, its return type, or both. Single statement closures implicitly return the value of their only statement.
>
> ```swift
> let mappedNumbers = numbers.map({ number in 3 * number })
> print(mappedNumbers)
> // Prints "[60, 57, 21, 36]"
> ```
>
> You can refer to parameters by number instead of by name—this approach is especially useful in very short closures. A closure passed as the last argument to a function can appear immediately after the parentheses. When a closure is the only argument to a function, you can omit the parentheses entirely.
>
> ```swift
> let sortedNumbers = numbers.sorted { $0 > $1 }
> print(sortedNumbers)
> // Prints "[20, 19, 12, 7]"
> ```



## 함수와 클로저

함수를 선언하기 위해 `func`을 사용하십시오. 함수의 이름과 소괄호 속의 전달인자들을 함께 적음으로써 함수를 호출하십시오. 매개변수 이름 및 타입을 함수의 반환 타입으로부터 분리하기 위해 `->`를 사용하십시오.

```swift
func greet(person: String, day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet(person: "Bob", day: "Tuesday")

```

> 실험
>
> `day` 매개변수를 삭제하십시오. 인사 속에 오늘의 점심 특선을 포함하기 위한 매개변수를 추가하십시오.

기본적으로, 함수는 매개변수 이름을 전달인자를 위한 레이블로 사용합니다. 직접 지은 전달인자 레이블은 매개변수 이름 앞에 적고, 전달인자 레이블을 사용하지 않으려면 `_`를 매개변수 이름 앞에 적으십시오.

``` swift
func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

복합적인 값을 만들기 위해 튜플을 사용하십시오 - 예를 들어, 함수로부터 다수의 값들을 반환하기 위해서입니다. 튜플의 요소들은 이름 또는 숫자를 통해 참조될 수 있습니다.

```swift
func calculateStatistics(scores: [Int]) -> (min: Int, max: Int, sum: Int) {
    var min = scores[0]
    var max = scores[0]
    var sum = 0

    for score in scores {
        if score > max {
            max = score
        } else if score < min {
            min = score
        }
        sum += score
    }

    return (min, max, sum)
}
let statistics = calculateStatistics(scores: [5, 3, 100, 3, 9])
print(statistics.sum)
// Prints "120"
print(statistics.2)
// Prints "120"
```

함수는 중첩될 수 있습니다. 중첩된 함수는 바깥쪽 함수에 선언된 변수에 접근할 수 있습니다. 함수 안의 길고 복잡한 코드를 정리하기 위해 중첩 함수를 사용할 수 있습니다.

``` swift
func returnFifteen() -> Int {
    var y = 10
    func add() {
        y += 5
    }
    add()
    return y
}
returnFifteen()
```

함수는 일급 타입(일급 객체)입니다. 이것은 함수가 반환 값으로 또 다른 함수를 반환할 수 있음을 의미합니다.

``` swift
func makeIncrementer() -> ((Int) -> Int) {
    func addOne(number: Int) -> Int {
        return 1 + number
    }
    return addOne
}
var increment = makeIncrementer()
increment(7)
```

함수는 전달인자의 하나로 다른 함수를 가질 수 있습니다.

``` swift
func hasAnyMatches(list: [Int], condition: (Int) -> Bool) -> Bool {
    for item in list {
        if condition(item) {
            return true
        }
    }
    return false
}
func lessThanTen(number: Int) -> Bool {
    return number < 10
}
var numbers = [20, 19, 7, 12]
hasAnyMatches(list: numbers, condition: lessThanTen)
```

함수는 사실 클로저의 특별한 경우입니다: 클로저는 나중에 호출될 수 있는 코드 블럭을 말합니다. 클로저 안의 코드는 클로저가 생성된 스코프 안에서 사용 가능한 변수와 함수 같은 것에 대한 접근권한을 가지고 있으며, 그것이 실행되었을 때 다른 스코프에 있더라도 마찬가지입니다 - 우리는 중첩 함수에서 이러한 예시를 본 바 있습니다. 클로저는 이름 없이 코드를 중괄호(`{}`)로 둘러쌈으로서 작성할 수 있습니다. 전달인자와 반환 타입을 코드 내용(body)으로부터 분리하기 위해 `in`을 사용하십시오.

(클로저를 선언한 시점과 사용한 시점이 다를 수 있다 - 함수도 마찬가지)

``` swift
numbers.map({ (number: Int) -> Int in
    let result = 3 * number
    return result
})
```

> 실험
>
> 모든 홀수에 대해 0을 반환하도록 클로저를 다시 작성해 보십시오.

클로저를 더 간결하게 작성하기 위한 몇 가지 선택 사항이 있습니다. 델리게이트(대리자)를 위한 콜백과 같이 클로저의 타입을 이미 알고 있을 때, 클로저의 매개변수나 리턴 타입 또는 둘 모두를 생략할 수 있습니다. 하나의 구문으로 이루어진 클로저는 암시적으로 그 구문의 값을 반환합니다.

``` swift
let mappedNumbers = numbers.map({ number in 3 * number })
print(mappedNumbers)
// Prints "[60, 57, 21, 36]"
```

매개변수를 이름 대신 숫자로 추론할 수도 있습니다 - 이 접근은 매우 짧은 클로저에서 특히 유용합니다. 함수의 마지막 전달인자로 전달된 클로저에 한 소괄호 뒤에 바로 나타낼 수 있습니다. 클로저가 함수의 유일한 전달인자일 때는 소괄호 양쪽을 생략할 수 있습니다.

``` swift
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
// Prints "[20, 19, 12, 7]"
```



## 영단어 정리

- argument 전달인자
- argument label 전달인자 레이블
- parameter name 매개변수 이름
- compound 복합적인 / 복합체
- refer 참조하다 / 참조하게 하다
- nested 내포된. 중첩의
- outer 바깥의
- first-class type 일급 타입
- surround 둘러싸다
- concisely 간결하게
- delegate 대표. (컴) 대리자 - 지정된 함수를 대신 실행해준다. 콜백 함수로 주로 사용
- approach 접근법, 처리방법
- multiple 다수의. 배수의.
- statistics 통계
- omit 생략하다. 빠뜨리다.
- organize 정리하다. 체계화하다

