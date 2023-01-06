# The Basics - Assertions and Preconditions (2)



> ### Debugging with Assertions
>
> You write an assertion by calling the [`assert(_:_:file:line:)`](https://developer.apple.com/documentation/swift/1541112-assert) function from the Swift standard library. 
>
> You pass this function an expression that evaluates to `true` or `false` and a message to display if the result of the condition is `false`. For example:
>
> ``` swift
> let age = -3
> assert(age >= 0, "A person's age can't be less than zero.")
> // This assertion fails because -3 isn't >= 0.
> ```
>
> In this example, code execution continues if `age >= 0` evaluates to `true`, that is, if the value of `age` is nonnegative. If the value of `age` is negative, as in the code above, then `age >= 0` evaluates to `false`, and the assertion fails, terminating the application.
>
> You can omit the assertion message—for example, when it would just repeat the condition as prose.
>
> ``` swift
> assert(age >= 0)
> ```
>
> If the code already checks the condition, you use the [`assertionFailure(_:file:line:)`](https://developer.apple.com/documentation/swift/1539616-assertionfailure) function to indicate that an assertion has failed. For example:
>
> ``` swift
> if age > 10 {
>  print("You can ride the roller-coaster or the ferris wheel.")
> } else if age >= 0 {
>  print("You can ride the ferris wheel.")
> } else {
>  assertionFailure("A person's age can't be less than zero.")
> }
> ```
>
> ### Enforcing Preconditions
>
> Use a precondition whenever a condition has the potential to be false, but must *definitely* be true for your code to continue execution. For example, use a precondition to check that a subscript isn’t out of bounds, or to check that a function has been passed a valid value.
>
> You write a precondition by calling the [`precondition(_:_:file:line:)`](https://developer.apple.com/documentation/swift/1540960-precondition) function. You pass this function an expression that evaluates to `true` or `false` and a message to display if the result of the condition is `false`. For example:
>
> ``` swift
> // In the implementation of a subscript...
> precondition(index > 0, "Index must be greater than zero.")
> ```
>
> You can also call the [`preconditionFailure(_:file:line:)`](https://developer.apple.com/documentation/swift/1539374-preconditionfailure) function to indicate that a failure has occurred—for example, if the default case of a switch was taken, but all valid input data should have been handled by one of the switch’s other cases.
>
> >  NOTE
> >
> > If you compile in unchecked mode (`-Ounchecked`), preconditions aren’t checked. The compiler assumes that preconditions are always true, and it optimizes your code accordingly. However, the `fatalError(_:file:line:)` function always halts execution, regardless of optimization settings.
> >
> > You can use the `fatalError(_:file:line:)` function during prototyping and early development to create stubs for functionality that hasn’t been implemented yet, by writing `fatalError("Unimplemented")` as the stub implementation. Because fatal errors are never optimized out, unlike assertions or preconditions, you can be sure that execution always halts if it encounters a stub implementation.

---

### Debugging with Assertions

Assertions로 디버깅하기

Swift standard library의 [`assert(_:_:file:line:)`](https://developer.apple.com/documentation/swift/1541112-assert) 함수를 호출함으로써 assertion을 작성합니다. 이 함수에 true나 false를 평가하는 표현식과, 조건의 결과가 false일 때 보여줄 메시지를 전달합니다. 예를 들어:

``` swift
let age = -3
assert(age >= 0, "A person's age can't be less than zero.")
// 이 assertion은 실패합니다. 왜냐하면 -3 >= 0이 옳지 않기 때문입니다.
```

이 예시에서, 코드 실행은 `age >= 0`이 true로 평가될 때, 즉 age의 값이 음수가 아닐 때 계속됩니다. 위 코드와 같이, 만약 age의 값이 음수이면, `age >= 0`은 false로 평가되고, assertion은 실패(fail)하며 애플리케이션을 종료합니다.

당신은 assertion의 메시지를 생략할 수 있습니다 - 예를 들어, 메시지가 조건문을 산문으로 그대로 반복하게 되는 경우입니다.

``` swift
assert(age >= 0)
```

만약 코드가 이미 조건식을 확인했다면, [`assertionFailure(_:file:line:)`](https://developer.apple.com/documentation/swift/1539616-assertionfailure) 함수를 사용해 assertion이 실패했음을 나타낼 수 있습니다. 예를 들어:

``` swift
if age > 10 {
    print("당신은 롤러코스터나 대관람차를 탈 수 있습니다.")
} else if age >= 0 {
    print("당신은 대관람차를 탈 수 있습니다.")
} else {
    assertionFailure("사람의 나이는 0보다 작을 수 없습니다.")
}
```

### Enforcing Preconditions

Precondition 실행

조건식이 false가 될 가능성이 있다면 언제든 precondition을 사용합니다. 하지만 당신의 코드가 계속 실행되기 위해서 precondition은 반드시 *확실히* true여야 합니다. 예를 들어, 서브스크립트가 범위를 벗어나지 않는지(out of bounds), 또는 함수에 유효한 값이 전달되었는지 확인하기 위해 precondition을 사용하십시오.

[`precondition(_:_:file:line:)`](https://developer.apple.com/documentation/swift/1540960-precondition) 함수를 호출함으로써 precondition을 작성합니다. 이 함수에 true나 false를 평가하는 표현식과, 조건식의 결과가 false일 때 보여줄 메시지를 전달해야 합니다. 예를 들어:

``` swift
// 서브스크립트의 구현에서...
precondition(index > 0, "인덱스는 반드시 0보다 커야 합니다.")
```

또한 실패가 발생했음을 나타내기 위해 [`preconditionFailure(_:file:line:)`](https://developer.apple.com/documentation/swift/1539374-preconditionfailure) 함수를 호출할 수도 있습니다 - 예를 들어, switch의 default case가 사용되었지만, 모든 유효한 입력 데이터가 switch의 다른 케이스들 중 하나에 의해 처리되어야 하는 경우입니다.

> 노트
>
> 만약 unchecked mode(`-Ounchecked`)에서 컴파일하면, preconditions는 체크되지 않습니다. 컴파일러는 preconditions가 항상 true인 것으로 가정하며, 그에 따라 당신의 코드를 최적화합니다. 하지만, `fatalError(_:file:line:)` 함수는 최적화 설정과는 관계없이 항상 실행을 중단시킵니다.
>
> 프로토타이핑이나 초기 개발 과정에서 아직 구현되지 않은 기능을 위한 토막을 만들기 위해, `fatalError("Unimplemented")`를 토막 구현으로 작성함으로써 `fatalError(_:file:line:)`함수를 사용할 수 있습니다. fatal error는 절대 최적화되지 않기 때문에, assertions나 preconditions와 다르게, 당신은 컴파일러가 토막 구현을 만났을 때 항상 실행이 중단될 것임을 확실히 할 수 있습니다.

---

## 단어 정리

- omit 생략하다
- prose 산문 (줄글)
- ferris wheel 대관람차
- implementation 구현
- handle 처리하다
- accordingly 그에 따라, 따라서
- assume 가정하다
- halt 멈추다, 중단시키다
- stub 토막
- functionality 기능. 기능성
- prototyping 프로토타이핑
- fatal error 치명적 에러
  - fatal 치명적인