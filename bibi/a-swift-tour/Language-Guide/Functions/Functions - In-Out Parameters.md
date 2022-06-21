# Functions - In-Out Parameters

> https://docs.swift.org/swift-book/LanguageGuide/Functions.html#:~:text=the%20variadic%20parameter.-,In%2DOut%20Parameters,-Function%20parameters%20are

함수의 파라미터(매개변수)는 기본적으로 상수입니다. 함수의 body에서 파라미터 값을 바꾸려는 시도는 컴파일 타임 에러를 발생시킵니다. 이는 실수로 파라미터 값을 바꿀 수 없음을 의미합니다. 만약 파라미터 값을 수정할 수 있는 함수를 원하고, 그 함수의 호출이 끝난 다음에도 그 변화를 유지하고 싶다면, 그 파라미터를 *in-out 파라미터* 로 대신 정의하십시오. 

파라미터의 타입 바로 앞에 `inout` 키워드를 놓음으로써 in-out 파라미터를 작성할 수 있습니다. in-out 파라미터는 함수 *내부(in)* 로  전달되고, 함수에 의해 수정되고, 원래 값을 대체하기 위해 함수 *외부(out)*로 다시 전달되는 값을 가집니다. in-out 파라미터의 동작과 연관 컴파일러 최적화에 대해 더 자세한 정보를 알기 위해서는, [In-Out Parameters](https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID545)를 참고하십시오.

in-out 파라미터에는 변수만을 아규먼트(argument)로 전달할 수 있습니다. 상수와 리터럴은 수정될 수 없기 때문에, 아규먼트로 상수나 리터럴을 전달할 수 없습니다. 함수에 의해 수정될 수 있음을 나타내기 위해, in-out 파라미터에 아규먼트를 전달할 때 변수의 이름 바로 앞에 앰퍼샌드(`&`)를 붙여야 합니다.

> 노트
>
> in-out 파라미터는 기본값을 가질 수 없으며, 가변 파라미터는 `inout`로 표기될 수 없습니다.

---

- argument 전달인자
  - parameter와 argument의 차이를 찾아보자.