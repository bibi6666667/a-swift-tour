### Implicitly Unwrapped Optionals

As described above, optionals indicate that a constant or variable is allowed to have “no value”. 

이전에 설명한 것 처럼, 옵셔널은 변수나 상수가 값이 없는걸 허락합니다.



Optionals can be checked with an `if` statement to see if a value exists, and can be conditionally unwrapped with optional binding to access the optional’s value if it does exist.

옵셔널은 만약 값이 존재하는지 이프문을 갖고 체크할 수 있습니다. 그리고 만약 옵셔널 값이 존재한다면 옵셔널 바인딩을 통해 조건적으로 값을 접근할 수 있습니다.



Sometimes it’s clear from a program’s structure that an optional will *always* have a value, after that value is first set. 

때떄로 프로그램 구조로부터 명백하다, 옵셔널이 처음 셋된 후로  항상 값을 갖는게 



In these cases, it’s useful to remove the need to check and unwrap the optional’s value every time it’s accessed, because it can be safely assumed to have a value all of the time.

이런 경우에, 값을 접근할때 마다 옵셔널 값을 벗기거나 체크하기 위해서 제거할 때 유용하다. ??? 왜냐하면 항상 값을 가지고 있다고 가정할 수 있기때문이다.



These kinds of optionals are defined as *implicitly unwrapped optionals*. 

이런 종류의 옵셔널은 암묵적 언래핑 옵셔널로 정의된다.



You write an implicitly unwrapped optional by placing an exclamation point (`String!`) rather than a question mark (`String?`) after the type that you want to make optional. 

옵셔널로 만들고 싶다면, 암묵적 옵셔널을 느낌표 대신 물음표를 타입 뒤에 작성한다.



Rather than placing an exclamation point after the optional’s name when you use it, you place an exclamation point after the optional’s type when you declare it.

당신이 사용할때 옵셔널 이름뒤에 느낌표를 붙이기 보다는 타입을 선언할때 느낌표를 붙입니다.



Implicitly unwrapped optionals are useful when an optional’s value is confirmed to exist immediately after the optional is first defined and can definitely be assumed to exist at every point thereafter. 

옵셔널 값이 처음 정의 된 후 즉시 존재한한다고 확인되어질때 그리고  매 순간 그 후로 명백하게 존재한다고 가정될 때 암묵적인 언래핑 옵셔널은 유용합니다.



The primary use of implicitly unwrapped optionals in Swift is during class initialization, as described in [Unowned References and Implicitly Unwrapped Optional Properties](https://docs.swift.org/swift-book/LanguageGuide/AutomaticReferenceCounting.html#ID55).

링크 설명처럼, 스위프트에서 암묵적 언래핑 옵셔널의 주 사용법은클래스 초기화이다.



implicitly: 암묵적인

Rather than: 보다는

thereafter: 그 후 부터

confirmed: 확인

definitely: 분명히