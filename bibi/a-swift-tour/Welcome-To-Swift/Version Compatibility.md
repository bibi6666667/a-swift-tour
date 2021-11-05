# A Swift Tour - Version Compatibility

> https://docs.swift.org/swift-book/GuidedTour/Compatibility.html

## Version Compatibility

> This book describes Swift 5.5, the default version of Swift that’s included in Xcode 13. You can use Xcode 13 to build targets that are written in either Swift 5.5, Swift 4.2, or Swift 4.
>
> When you use Xcode 13 to build Swift 4 and Swift 4.2 code, most Swift 5.5 functionality is available. That said, the following changes are available only to code that uses Swift 5.5 or later:
>
> - Functions that return an opaque type require the Swift 5.1 runtime.
> - The `try?` expression doesn’t introduce an extra level of optionality to expressions that already return optionals.
> - Large integer literal initialization expressions are inferred to be of the correct integer type. For example, `UInt64(0xffff_ffff_ffff_ffff)` evaluates to the correct value rather than overflowing.
>
> Concurrency requires Swift 5.5 or later, and a version of the Swift standard library that provides the corresponding concurrency types. On Apple platforms, set a deployment target of at least iOS 15, macOS 12, tvOS 15, or watchOS 8.0.
>
> A target written in Swift 5.5 can depend on a target that’s written in Swift 4.2 or Swift 4, and vice versa. This means, if you have a large project that’s divided into multiple frameworks, you can migrate your code from Swift 4 to Swift 5.5 one framework at a time.

## 버전 호환성

이 책은 Xcode 13에 포함된 Swift의 기본 버전인 Swift 5.5에 대해 서술하고 있습니다. 당신은 Swift 5.5, Swift 4.2, Swift 4로 쓰여진 타겟을 빌드하기 위해 Xcode 13을 사용할 수 있습니다.

Swift 4와 Swift 4.2 코드를 빌드하기 위해 Xcode 13을 사용할 때, Swift 5.5의 대부분의 기능성이 사용 가능합니다. 그렇긴 하지만, 아래의 변화들은 Swift 5.5 이상 버전을 사용하는 코드에서만 사용 가능합니다 :

- 불분명 타입을 반환하는 함수들은 실행 시간에 Swift 5.1을 요구합니다.
- `try?` 표현은 이미 옵셔널을 반환하는 표현들에 대한 추가적인 수준의 선택성을 소개하지 않습니다.
- 큰 정수 리터럴 초기화 표현은 올바른 정수 타입이 되도록 추론됩니다. 예를 들어, `UInt64(0xffff_ffff_ffff_ffff)` 는 오버플로되기보다는 올바른 정수 타입으로 평가합니다.

동시 실행은 Swift 5.5 이상과, 상응하는 동시 실행 타입들을 제공하는  Swift 표준 라이브러리를 요구합니다. Apple 플랫폼들에서, 배포 타겟을 최소한 iOS 15, macOS 12, tvOS 15, watchOS 8.0으로 설정하십시오.

Swift 5.5로 작성된 타겟은 Swift 4.2 또는 Swift 4로 작성된 타겟에 의존할 수 있으며, 그 반대도 성립합니다. 이는 만약 당신이 여러 개의 프레임워크들로 나뉘어진 거대한 프로젝트를 가지고 있다면, 당신은 Swift 4에서 Swift 5.5로 한 번에 한 프레임워크를 옮길 수 있음을 의미합니다.

---

## 단어 정리

- compatibility 호환성
  - compatible 호환이 되는.
- compete 경쟁하다
- functionality 기능성
  - function 기능
- opaque 불투명한 [오페그]
  - opaque type 불분명 타입
- optionality 선택성.
- literal 글자 그대로의.
- infer 추론하다
- evaluate 평가하다
- overflow 넘치다, 넘침
- concurrency 동시 실행. 동시성
- correspond 부합하다. ..에 상응하다. 
- deployment 전개. 배치
  - 개발에서는 배포의 의미. (deploy, deployment)
- migrate 이주하다. 옮기다.

- included in ...에 포함되다
- that said 그렇긴 하지만
  - with that (being) said 에서 with 이 생략된 표현
- available to ... 가 이용 가능한.
- runtime 실행 시간
- target 대상

---

> Large integer literal initialization expressions are inferred to **be of** the correct integer type.

- be of 명사 = be 형용사 로 해석한다.
- 명사를 형용사로 꾸미고 싶을 때 사용하는 표현이다.
  - be of help, be of use 등의 형태로 많이 사용 (= be helpful, be useful 의 의미)
  - http://www.rainenglish.com/RainEnglishQandA12/2041
  - https://blog.naver.com/PostView.naver?blogId=shy1004jh&logNo=221581686878&parentCategoryNo=&categoryNo=72&viewDate=&isShowPopularPosts=true&from=search
- 문법적으로는 `주어 be (주어) of ...` 이 `주어 be of ...` 으로 표현(생략)된 것이라고 볼 수 있다.
  - 즉 위 예문의 경우 Large integer literal initialization expressions are inferred to be expressions of the correct integer type. 과 같다고 볼 수 있다.
  - https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=koreiskii&logNo=220329948603

- deployment target 배포 대상

- one at a time 한 번에 하나씩.
  - one 목적어 at a time (목적어)를 한 번에 하나씩.