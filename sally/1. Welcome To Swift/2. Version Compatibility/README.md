## [Version Compatibility](https://docs.swift.org/swift-book/GuidedTour/Compatibility.html)

This book describes Swift 5.5, the default version of Swift that’s included in Xcode 13. You can use Xcode 13 to build targets that are written in either Swift 5.5, Swift 4.2, or Swift 4.

When you use Xcode 13 to build Swift 4 and Swift 4.2 code, most Swift 5.5 functionality is available. That said, the following changes are available only to code that uses Swift 5.5 or later:

- Functions that return an opaque type require the Swift 5.1 runtime.
- The try? expression doesn’t introduce an extra level of optionality to expressions that already return optionals.
- Large integer literal initialization expressions are inferred to be of the correct integer type. For example, UInt64(0xffff_ffff_ffff_ffff) evaluates to the correct value rather than overflowing.

Concurrency requires Swift 5.5 or later, and a version of the Swift standard library that provides the corresponding concurrency types. On Apple platforms, set a deployment target of at least iOS 15, macOS 12, tvOS 15, or watchOS 8.0.

A target written in Swift 5.5 can depend on a target that’s written in Swift 4.2 or Swift 4, and vice versa. This means, if you have a large project that’s divided into multiple frameworks, you can migrate your code from Swift 4 to Swift 5.5 one framework at a time.

## 버전 호환성

이 책은 Xcode 13에 포함되는 스위프트 디폴트 버전인 스위프트 5.5에 대해 설명합니다. 당신은 스위프트 5.5, 스위프트 4.2, 스위프트 4 중에 하나로 작성된 타겟을 빌드하기 위해서 Xcode 13을 사용할 수 있습니다. 

스위프트 4와 스위프트 4.2를 빌드하기 위해 Xcode 13을 사용할 때, 대부분의 스위프트 5.5의 기능을 사용할 수 있습니다. 그렇지만, 다음 변화들은 오직 스위프트 5.5와 그 이후 버전을 사용한 코드에서만 가능합니다. 

- 불투명한 타입을 반환하는 함수는 스위프트 5.1 런타임을 요구합니다. 
- try? 표현식이 이미 옵셔널을 반환하는 표현식에 추가적인 수준의 옵션을 제안하지 않습니다. 
- 큰 정수 리터럴 초기화 표현식은 명확한 타입에 의해 추론되어집니다. 예를 들어, UInt64는 오버플로우 되지 않고 더 정확한 값으로 평가됩니다. 

동시성은 스위프트 5.5 혹은 그 이후의 버전과, 해당 동시성 타입에 상응하는 것을 제공하는 스위프트 표준 라이브러리 버전을 요구합니다. 애플 플랫폼에서는 최소한 iOS 15, macOS 12, tvOS 15, 혹은 watchOS 8.0 이상을 배포 대상으로 설정합니다. 

스위프트 5.5로 쓰여진 타겟은 스위프트 4.2, 혹은 스위프트 4로 쓰여진 타겟에 의존할 수 있고, 그 반대도 마찬가지 입니다. 즉, 당신이 여러 개의 프레임워크로 이루어진 큰 프로젝트가 있다면, 한번에 하나의 프레임워크씩 스위프트 4에서 스위프트 5.5로 이식시킬 수 있습니다. 


</br>

_\* compatibility : 호환성_</br>
_\* (with) that (being) said : 그런데도, 앞 내용과 반대로 ([참고](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=dongsu0505&logNo=221151078042))_</br>
_\* only to : \~에만_</br>
_\* introduce A to B : A를 B에게 소개하다. 도입하다._</br>
_\* are inferred to : \~로 추론된다_</br>
_\* be of : \~의_</br>
_\* corresponding : 상응하는_</br>
_\* vice versa : 그 반대도 마찬가지_</br>
_\* one at a time : 한 번에 하나씩_</br>

