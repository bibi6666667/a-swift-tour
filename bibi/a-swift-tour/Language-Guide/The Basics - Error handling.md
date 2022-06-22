# The Basics - Error handling

## Error Handling

You use *error handling* to respond to error conditions your program may encounter during execution.

In contrast to optionals, which can use the presence or absence of a value to communicate success or failure of a function, error handling allows you to determine the underlying cause of failure, and, if necessary, propagate the error to another part of your program.

When a function encounters an error condition, it *throws* an error. That function’s caller can then *catch* the error and respond appropriately.

``` swift
func canThrowAnError() throws {
    // this function may or may not throw an error
}
```

A function indicates that it can throw an error by including the `throws` keyword in its declaration. When you call a function that can throw an error, you prepend the `try` keyword to the expression.

Swift automatically propagates errors out of their current scope until they’re handled by a `catch` clause.

``` swift
do {
    try canThrowAnError()
    // 에러가 발생하지 않았습니다(no error was thrown)
} catch {
    // 에러가 발생했습니다(an error was thrown)
}
```

A `do` statement creates a new containing scope, which allows errors to be propagated to one or more `catch` clauses.

Here’s an example of how error handling can be used to respond to different error conditions:

``` swift
func makeASandwich() throws {
    // ...
}

do {
    try makeASandwich()
    eatASandwich()
} catch SandwichError.outOfCleanDishes {
    washDishes()
} catch SandwichError.missingIngredients(let ingredients) {
    buyGroceries(ingredients)
}
```

In this example, the `makeASandwich()` function will throw an error if no clean dishes are available or if any ingredients are missing. Because `makeASandwich()` can throw an error, the function call is wrapped in a `try` expression. By wrapping the function call in a `do` statement, any errors that are thrown will be propagated to the provided `catch` clauses.

If no error is thrown, the `eatASandwich()` function is called. If an error is thrown and it matches the `SandwichError.outOfCleanDishes` case, then the `washDishes()` function will be called. If an error is thrown and it matches the `SandwichError.missingIngredients` case, then the `buyGroceries(_:)` function is called with the associated `[String]` value captured by the `catch` pattern.

Throwing, catching, and propagating errors is covered in greater detail in [Error Handling](https://docs.swift.org/swift-book/LanguageGuide/ErrorHandling.html).

---

## Error Handling

에러 처리

당신의 프로그램이 실행 중에 마주칠 수 있는 에러 상황에 응답하기 위해 *에러 처리*를 사용할 수 있습니다.

함수의 성공 또는 실패를 뜻하는 값의 존재 또는 부재를 나타낼 수 있는 옵셔널과 반대로, 에러 처리는 실패의 근본적인 원인을 파악할 수 있게 해 주며, 만약 필요하다면, 프로그램의 다른 부분에 에러를 전파합니다.

함수가 에러 상황을 맞게 되면, 에러를 *던집니다(throw)*. 그러면 그 함수의 호출자는 에러를 *잡아(catch)* 적절히 응답할 수 있습니다.

``` swift
func canThrowAnError() throws {
    // 이 함수는 에러를 던질 수도 있고, 던지지 않을 수도 있습니다.
}
```

함수는 그 선언부에 `throws`라는 키워드를 포함함으로써 그것이 에러를 던질 수 있음을 나타낼 수 있습니다. 에러를 던질 수 있는 함수를 호출할 때, 표현식 앞에 `try` 키워드를 붙이십시오.

스위프트는 에러가 `catch` 문으로 처리될 때 까지 현재 스코프 밖으로 자동으로 에러를 알립니다.

``` swift
do {
    try canThrowAnError()
    // 에러가 발생하지 않았습니다(no error was thrown)
} catch {
    // 에러가 발생했습니다(an error was thrown)
}
```

`do` 구문은 에러를 하나 이상의 `catch`문으로 전파할 수 있도록 하는 새로운 스코프 범위를 만듭니다.

여기에 에러 처리가 어떻게 서로 다른 에러 조건에 응답하도록 사용될 수 있는지에 대한 예시가 있습니다:

``` swift
func makeASandwich() throws {
    // ...
}

do {
    try makeASandwich()
    eatASandwich()
} catch SandwichError.outOfCleanDishes {
    washDishes()
} catch SandwichError.missingIngredients(let ingredients) {
    buyGroceries(ingredients)
}
```

이 예시에서, `makeASandwich()` 함수는 깨끗한 접시가 없거나, 없는 재료가 있을 때 에러를 던집니다. `makeASandwich()`가 에러를 던질 수 있기 때문에, 함수 호출은 `try` 표현식으로 감싸져 있습니다. `do`구문으로 감싸 함수를 호출함으로써, 던져지는 모든 에러는 제공되는 `catch`문으로 전파될 것입니다.

만약 어떤 에러도 던져지지 않는다면, `eatASandwich()` 함수가 호출됩니다. 만약 에러가 던져지고 그것이 `SandwichError.outOfCleanDishes`와 일치한다면, `washDishes()` 함수가 호출될 것입니다. 만약 에러가 던져지고 그것이 `SandwichError.missingIngredients`와 일치한다면, `catch`문으로 캡처한 연관값 [String]과 함께 `buyGroceries(_:)`함수가 호출될 것입니다.

에러를 던지고, 잡고, 전파하는 것은 [Error Handling](https://docs.swift.org/swift-book/LanguageGuide/ErrorHandling.html)에 훨씬 자세히 설명되어 있습니다.

---

## 단어 정리

- underlying 근본적인
- propagate  전파하다. 선전하다.
- prepend 앞에 붙이다
- clause 절, 구