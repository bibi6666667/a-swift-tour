## [Version Compatibility](https://docs.swift.org/swift-book/GuidedTour/Compatibility.html)

This book describes Swift 5.5, the default version of Swift that’s included in Xcode 13. You can use Xcode 13 to build targets that are written in either Swift 5.5, Swift 4.2, or Swift 4.

When you use Xcode 13 to build Swift 4 and Swift 4.2 code, most Swift 5.5 functionality is available. That said, the following changes are available only to code that uses Swift 5.5 or later:

Functions that return an opaque type require the Swift 5.1 runtime.
The try? expression doesn’t introduce an extra level of optionality to expressions that already return optionals.
Large integer literal initialization expressions are inferred to be of the correct integer type. For example, UInt64(0xffff_ffff_ffff_ffff) evaluates to the correct value rather than overflowing.
Concurrency requires Swift 5.5 or later, and a version of the Swift standard library that provides the corresponding concurrency types. On Apple platforms, set a deployment target of at least iOS 15, macOS 12, tvOS 15, or watchOS 8.0.

A target written in Swift 5.5 can depend on a target that’s written in Swift 4.2 or Swift 4, and vice versa. This means, if you have a large project that’s divided into multiple frameworks, you can migrate your code from Swift 4 to Swift 5.5 one framework at a time.

## 버전 호환성

<!-- _\* 단어 : 뜻_ -->