## The Basics - Assertions and Preconditions (1)

*Assertions* and *preconditions* are checks that happen at runtime. You use them to make sure an essential condition is satisfied before executing any further code. If the Boolean condition in the assertion or precondition evaluates to `true`, code execution continues as usual. If the condition evaluates to `false`, the current state of the program is invalid; code execution ends, and your app is terminated.

You use assertions and preconditions to express the assumptions you make and the expectations you have while coding, so you can include them as part of your code. Assertions help you find mistakes and incorrect assumptions during development, and preconditions help you detect issues in production.

In addition to verifying your expectations at runtime, assertions and preconditions also become a useful form of documentation within the code. Unlike the error conditions discussed in [Error Handling](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID515) above, assertions and preconditions aren’t used for recoverable or expected errors. Because a failed assertion or precondition indicates an invalid program state, there’s no way to catch a failed assertion.

Using assertions and preconditions isn’t a substitute for designing your code in such a way that invalid conditions are unlikely to arise. However, using them to enforce valid data and state causes your app to terminate more predictably if an invalid state occurs, and helps make the problem easier to debug. Stopping execution as soon as an invalid state is detected also helps limit the damage caused by that invalid state.

The difference between assertions and preconditions is in when they’re checked: Assertions are checked only in debug builds, but preconditions are checked in both debug and production builds. In production builds, the condition inside an assertion isn’t evaluated. This means you can use as many assertions as you want during your development process, without impacting performance in production.

---

## Assertions and Preconditions

assertions과 preconditions (단정과 전제조건)

*Assertions*과 *preconditions*는 실행 중에 발생하는 검사입니다. 당시는 코드를 더 실행하기 전에 필요한 조건이 만족되었는지 확실히 하기 위해 이들을 사용할 수 있습니다. 만약 assertion 또는 precondition의 불리언 조건이 true로 평가되면, 코드 실행은 평소처럼 계속됩니다. 만약 조건이 false로 평가되면, 프로그램의 현재 상태가 무효화됩니다; 코드 실행이 멈추고, 당신의 애플리케이션이 종료됩니다.

당신이 코딩을 하는 동안 만든 가정과 생긴 기대를 표현하고, 그것을 당신의 코드 일부로 포함시키기 위해 assertions과 preconditions를 사용합니다. assertions는 개발 중에 실수와 잘못된 가정을 찾는 것을 도와주며, preconditions는 운영 중에 문제를 찾는 것을 도와줍니다.

실행 시점에 기대를 검증하는 것에 더해서, assertions와 preconditions는 또한 코드 내에서 유용한 형태의 문서가 됩니다. 위의 [Error Handling](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID515)에서 다룬 에러 조건들과 다르게, assertions와 preconditions는 회복할 수 있거나 기대되는 에러들에는 사용되지 않습니다. 실패한 assertion 또는 precondition은 유효하지 않은 프로그램 상태를 나타내기 때문에, 실패한 assertion을 잡을(catch) 방법은 없습니다.

assertions와 preconditions를 사용하는 것은 당신의 코드를 유효하지 않은 조건이 잘 발생하지 않도록 만드는 것을 대신할 수 없습니다. 하지만, 유효한 데이터와 상태가 되도록 그것들을 사용하면 당신의 애플리케이션이 더 예측가능하게 종료되고, 문제를 디버깅하는 것이 더 쉬워집니다. 또한 유효하지 않은 상태가 감지되자마자 실행을 멈추는 것은 유효하지 않은 상태로부터 오는 손실을 최소화하는 것을 돕습니다.

assertions와 preconditions의 차이점은 그것들이 확인되는 시간입니다: asssertions는 디버그 빌드 시점에만 확인되지만, preconditions는 디버그와 운영 빌드 시점 모두에 확인됩니다. 운영을 위한 빌드에서는, assertion의 조건들이 평가되지 않습니다. 이것은 당신이 운영에 대한 성능에 영향을 주지 않고, 개발 과정 동안 원하는 만큼 많은 assertions를 사용할 수 있음을 의미합니다.

---

## 단어 정리

- Assertion 단정. 주장.
- precondition 전제조건
- check (n) 검사
- invalid 유효하지 않은
- express 표현하다
- assumption 가정
- expectation 기대
- production 운영 환경?
  - in production 운영에서 ( = 앱스토어에 출시되어 서비스되고 있는 앱)
- issue 문제
- verify 검증하다
- recoverable 회복할 수 있는
- substitute (명) 대리자 (동) 역할을 대신하다.
  - substitute for ... ...를 대신하다
- arise 생기다. 일어나다.
- enforce 억지로 시키다. 시행하다