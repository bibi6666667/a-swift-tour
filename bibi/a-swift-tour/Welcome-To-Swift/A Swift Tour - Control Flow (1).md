# A Swift Tour - Control Flow (1)

>## Control Flow
>
>Use `if` and `switch` to make conditionals, and use `for`-`in`, `while`, and `repeat`-`while` to make loops. Parentheses around the condition or loop variable are optional. Braces around the body are required.
>
>```swift
>let individualScores = [75, 43, 103, 87, 12]
>var teamScore = 0
>for score in individualScores {
>    if score > 50 {
>        teamScore += 3
>    } else {
>        teamScore += 1
>    }
>}
>print(teamScore)
>// Prints "11"
>```
>
>In an `if` statement, the conditional must be a Boolean expression—this means that code such as `if score { ... }` is an error, not an implicit comparison to zero.
>
>You can use `if` and `let` together to work with values that might be missing. These values are represented as optionals. An optional value either contains a value or contains `nil` to indicate that a value is missing. Write a question mark (`?`) after the type of a value to mark the value as optional.
>
>```swift
>var optionalString: String? = "Hello"
>print(optionalString == nil)
>// Prints "false"
>
>var optionalName: String? = "John Appleseed"
>var greeting = "Hello!"
>if let name = optionalName {
>    greeting = "Hello, \(name)"
>}
>```
>
>
>
>> EXPERIMENT
>>
>> Change `optionalName` to `nil`. What greeting do you get? Add an `else` clause that sets a different greeting if `optionalName` is `nil`.
>
>If the optional value is `nil`, the conditional is `false` and the code in braces is skipped. Otherwise, the optional value is unwrapped and assigned to the constant after `let`, which makes the unwrapped value available inside the block of code.
>
>Another way to handle optional values is to provide a default value using the `??` operator. If the optional value is missing, the default value is used instead.
>
>``` swift
>let nickname: String? = nil
>let fullName: String = "John Appleseed"
>let informalGreeting = "Hi \(nickname ?? fullName)"
>```
>
>Switches support any kind of data and a wide variety of comparison operations—they aren’t limited to integers and tests for equality.
>
>``` swift
>let vegetable = "red pepper"
>switch vegetable {
>case "celery":
>    print("Add some raisins and make ants on a log.")
>case "cucumber", "watercress":
>    print("That would make a good tea sandwich.")
>case let x where x.hasSuffix("pepper"):
>    print("Is it a spicy \(x)?")
>default:
>    print("Everything tastes good in soup.")
>}
>// Prints "Is it a spicy red pepper?"
>```
>
>> EXPERIMENT
>>
>> Try removing the default case. What error do you get?
>>
>> : `Switch must be exhaustive`



## 제어 흐름 (1)

조건문을 만들기 위해 `if` 와 `switch`를, 그리고 반복문을 만들기 위해 `for-in`, `while`, `repeat-while` 을 사용하십시오. 조건문이나 반복문 주위의 소괄호는 선택 사항입니다. 몸통 주변의 중괄호는 필수 사항입니다.

```swift
let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individualScores {
    if score > 50 {
        teamScore += 3
    } else {
        teamScore += 1
    }
}
print(teamScore)
// Prints "11"
```

`if` 구문에서, 조건문은 반드시 Boolean 표현식이어야 합니다 - 이는 `if score { ... }` 와 같은 코드는 0에 대한 암시적인 비교가 아니라 에러임을 의미합니다.

없을 수 있는 값을 다루기 위해 `if` 와  `let` 을 함께 사용할 수도 있습니다. 대표적으로 옵셔널과 같은 값이 있습니다. 옵셔널 값은 값을 담고 있거나, 값이 없음을 나타내기 위해 `nil`을 담고 있습니다. 값을 옵셔널로 표시하기 위해 값의 타입 뒤에 물음표(`?`) 를 붙이십시오.

```swift
var optionalString: String? = "Hello"
print(optionalString == nil)
// Prints "false"

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
```

> 실험
>
> `optionalName` 을  `nil` 로 바꾸십시오. 어떤 인사를 받게 됩니까? (없음)
>
> `optionalName` 이 `nil` 일 때 받기 위한 다른 인사를 지정하는 `else` 절을 추가하십시오.

만약 옵셔널 값이 nil 이라면, 조건문은 false가 되고 중괄호 속의 코드는 건너뛰게 됩니다. 그렇지 않으면, 옵셔널 값은 벗겨지고 let 뒤의 상수에 할당되어 벗겨진 값을 코드 블록 내에서 쓸 수 있게 됩니다.

옵셔널 값을 다루는 다른 방법은 `??` 연산자를 사용해 기본값을 제공하는 것입니다. 만약 옵셔널의 값이 없다면, 기본값이 대신 사용됩니다.

``` swift
let nickname: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickname ?? fullName)"
```

switch문은 모든 종류의 데이터와 넓고 다양한 범위의 비교 연산을 지원합니다 - switch문은 정수형과 동등성을 위한 테스트에 한정되지 않습니다.

``` swift
let vegetable = "red pepper"
switch vegetable {
case "celery":
    print("Add some raisins and make ants on a log.")
case "cucumber", "watercress":
    print("That would make a good tea sandwich.")
case let x where x.hasSuffix("pepper"):
    print("Is it a spicy \(x)?")
default:
    print("Everything tastes good in soup.")
}
// Prints "Is it a spicy red pepper?"
```

> 실험
>
> default 케이스를 삭제해 보십시오. 어떤 에러를 보게 됩니까?
>
> `Switch must be exhaustive` : switch문은 포괄적이어야 합니다.



## 단어 정리



## 영단어 정리

- control flow 제어 흐름
- conditional 조건부의 / 조건문
- implicit 암시하는
- comparison 비교
- missing 없어진.
- represent 대표하다
- clause 절
- otherwise 그렇지 않으면?
- exhaustive 철저한. 빠짐없는.
- unwrap (포장 등을) 풀다. 벗기다.
- operation (컴) 연산
- equality 동등성

