> https://docs.swift.org/swift-book/LanguageGuide/Closures.html#:~:text=ON%20THIS%20PAGE-,Closures,-Closures%20are%20self

클로저는 자급적인 기능성 블럭이며, 당신의 코드 내에서 전달되거나 사용될 수 있습니다. 스위프트에서의 클로저는 C와 Objective-C의 blocks와 비슷하며, 다른 프로그래밍 언어의 lambdas와 비슷합니다.

클로저는 자신이 정의된 문맥으로부터 어떤 상수나 변수를 참조를 캡처(capture)하고 저장할 수 있습니다. 이것은 그 상수나 변수를 *둘러싸는(closing over)* 것이라고 알려져 있습니다. 스위프트는 캡처에 대한 모든 메모리 관리를 당신을 위해 다루어 줍니다.

> 노트
> 캡처(capturing)의 개념에 대해 익숙하지 않더라도 걱정하지 마십시오. 아래의 [Capturing Values](https://docs.swift.org/swift-book/LanguageGuide/Closures.html#ID103)에 자세히 설명되어 있습니다.

 [Functions](https://docs.swift.org/swift-book/LanguageGuide/Functions.html)에 설명된 전역 및 중첩 함수는, 사실 클로저의 특별한 유형입니다. 클로저는 아래의 셋 중 하나의 형태를 가집니다:
- 전역 함수는 이름을 가지고, 어떤 값도 캡처하지 않는 클로저입니다.
- 중첩 함수는 이름을 가지고, 자신을 둘러싼 함수로부터 값을 캡처할 수 있습니다.
- 클로저 표현식은 이름이 없고, 경량화된 문법으로 작성되며, 주변 문맥으로부터 값을 캡처할 수 있습니다.
스위프트의 클로저 표현식은 깔끔하고 명확한 스타일을 가지며, 일반적인 시나리오에서 간결하고 군더더기 없는 문법을 지향하도록 최적화 되어 있습니다. 이러한 최적화는 아래의 사항을 포함합니다:
- 문맥으로부터 파라미터와 리턴값의 타입을 추론합니다
- 한 줄로 된 표현식의 클로저에 암묵적으로 return을 합니다
- 약식 아규먼트 네임
- 후행 클로저(trailing closure) 문법

## 클로저 표현
[Nested Functions](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID178)에 소개된 대로, 중첩 함수는 더 큰 함수이 일부로서 자급적인 코드 블럭을 이름짓고 정의하는 편리한 수단입니다. 하지만, 가끔은 완전한 선언과 이름 없이 함수 같은 구조의 짧은 버전을 작성하는 것이 유용합니다. 이것은 당신이 하나 이상의 아규먼트를 갖는 함수를 받는 함수나 메서드를 다룰 때 특히 그렇습니다.

클로저 표현식은 간결하고 집중된 문맥으로 인라인 클로저를 작성하는 방법입니다. 클로저 표현식은 의도나 명확성을 잃지 않고 클로저를 약식으로 작성하기 위한 몇몇 최적화 문법을 제공합니다. 아래의 클로저 표현식 예시들은 반복적으로 `sorted(by:)` 라는 하나의 예제 메서드를 개선하면서도, 각각의 표현들이 더 간결하면서도 같은 기능을 하는 표현식으로 이러한 최적화를 설명합니다.

---

## 단어정리
- self-contained 자급적인
- close over : 감싸다. 둘러싸다. (to surround and cover somebody/something)
- enclosing : 둘러싸다
- clutter-free : 군더더기 없는
- clear : 명확한
- shorthand : 약식의
- trailing : 후행
- means : 수단
- particularly 특히
- inline : 일렬로 배열된 것의 일부로. (with parts arranged in a line)
- illustrate : 예를 들어 설명하다
- refine : 개선하다
- succinct : 간결한