# The Basics - Constants and Variables



> ## Constants and Variables
>
> Constants and variables associate a name (such as `maximumNumberOfLoginAttempts` or `welcomeMessage`) with a value of a particular type (such as the number `10` or the string `"Hello"`). The value of a *constant* can’t be changed once it’s set, whereas a *variable* can be set to a different value in the future.
>
> ### Declaring Constants and Variables
>
> Constants and variables must be declared before they’re used. You declare constants with the `let` keyword and variables with the `var` keyword. Here’s an example of how constants and variables can be used to track the number of login attempts a user has made:
>
> ``` swift
> let maximumNumberOfLoginAttempts = 10
> var currentLoginAttempt = 0
> ```
>
> This code can be read as:
>
> “Declare a new constant called `maximumNumberOfLoginAttempts`, and give it a value of `10`. Then, declare a new variable called `currentLoginAttempt`, and give it an initial value of `0`.”
>
> In this example, the maximum number of allowed login attempts is declared as a constant, because the maximum value never changes. The current login attempt counter is declared as a variable, because this value must be incremented after each failed login attempt.
>
> You can declare multiple constants or multiple variables on a single line, separated by commas:
>
> ``` swift
> var x = 0.0, y = 0.0, z = 0.0
> ```
>
> NOTE
>
> If a stored value in your code won’t change, always declare it as a constant with the `let` keyword. Use variables only for storing values that need to be able to change.



## 상수와 변수

상수와 변수는 이름 (예를 들어 `maximumNumberOfLoginAttempts` 이나 `welcomeMessage`) 과 특정한 타입의 값 (예를 들어 숫자 `10` 이나 문자열 `"Hello"`)을 연관짓습니다. 상수의 값은 한 번 설정되면 바뀔 수 없는 반면, 변수는 추후에 다른 값으로 설정될 수 있습니다.

### 상수와 변수 선언

상수와 변수는 사용되기 전에 반드시 선언되어야 합니다. `let` 키워드로 상수를 선언하고 `var` 키워드로 변수를 선언하십시오. 여기에 유저가 만든 로그인 시도 횟수를 추적하는 데에 상수와 변수가 어떻게 사용될 수 있는지에 대한 예시가 있습니다 :

``` swift
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
```

이 코드는 이렇게 읽을 수 있습니다 : 

"`maximumNumberOfLoginAttempts`라는 새로운 상수 하나를 선언하고, 그 값을 `10`으로 한다. 그런 다음, `currentLoginAttempt`라는 새로운 변수 하나를 선언하고, 그 값을 `0`으로 한다."

이 예시에서, 허용된 로그인 시도의 최대 횟수는 상수로 선언되었으며, 그 이유는 최대 값은 절대 변하지 않기 때문입니다. 현재 로그인 시도 카운터는 변수로 선언되었으며, 그 이유는 이 값은 로그인 시도가 실패할 때 마다 반드시 증가할 것이기 때문입니다.

쉼표로 구분하여 여러 개의 변수 또는 여러 개의 상수를 한 줄에 선언할 수 있습니다 :

``` swift
var x = 0.0, y = 0.0, z = 0.0
```

> 노트
>
> 만약 당신의 코드에서 저장된 값이 바뀌지 않을 것이라면, 항상 `let` 키워드와 함께 상수로 선언하십시오. 오직 바뀔 수 있어야 하는 값을 저장할 때만 변수를 사용하십시오.



## 단어 정리

- whereas 반면
- attempt 시도
- associate 연관짓다