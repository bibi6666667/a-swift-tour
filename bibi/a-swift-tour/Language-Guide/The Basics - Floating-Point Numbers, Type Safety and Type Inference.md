# The Basics - Floating-Point Numbers, Type Safety and Type Inference
# Floating-Point Numbers
Floating-point numbers are numbers with a fractional component, such as 3.14159, 0.1, and -273.15.
Floating-point types can represent a much wider range of values than integer types, and can store numbers that are much larger or smaller than can be stored in an Int. Swift provides two signed floating-point number types:
* Double represents a 64-bit floating-point number.
* Float represents a 32-bit floating-point number.
> NOTE  
> Double has a precision of at least 15 decimal digits, whereas the precision of Float can be as little as 6 decimal digits. The appropriate floating-point type to use depends on the nature and range of values you need to work with in your code. In situations where either type would be appropriate, Double is preferred.  

# Type Safety and Type Inference
Swift is a type-safe language. A type safe language encourages you to be clear about the types of values your code can work with. If part of your code requires a String, you can’t pass it an Int by mistake.
Because Swift is type safe, it performs type checks when compiling your code and flags any mismatched types as errors. This enables you to catch and fix errors as early as possible in the development process.
Type-checking helps you avoid errors when you’re working with different types of values. However, this doesn’t mean that you have to specify the type of every constant and variable that you declare. If you don’t specify the type of value you need, Swift uses type inference to work out the appropriate type. Type inference enables a compiler to deduce the type of a particular expression automatically when it compiles your code, simply by examining the values you provide.
Because of type inference, Swift requires far fewer type declarations than languages such as C or Objective-C. Constants and variables are still explicitly typed, but much of the work of specifying their type is done for you.
Type inference is particularly useful when you declare a constant or variable with an initial value. This is often done by assigning a literal value (or literal) to the constant or variable at the point that you declare it. (A literal value is a value that appears directly in your source code, such as 42 and 3.14159 in the examples below.)
For example, if you assign a literal value of 42 to a new constant without saying what type it is, Swift infers that you want the constant to be an Int, because you have initialized it with a number that looks like an integer:
``` swift
let meaningOfLife = 42
// meaningOfLife is inferred to be of type Int
```
Likewise, if you don’t specify a type for a floating-point literal, Swift infers that you want to create a Double:
``` swift
let pi = 3.14159
// pi is inferred to be of type Double
```
Swift always chooses Double (rather than Float) when inferring the type of floating-point numbers.
If you combine integer and floating-point literals in an expression, a type of Double will be inferred from the context:
``` swift
let anotherPi = 3 + 0.14159
// anotherPi is also inferred to be of type Double
```
The literal value of 3 has no explicit type in and of itself, and so an appropriate output type of Double is inferred from the presence of a floating-point literal as part of the addition.

- - - -
## Floating-Point Numbers
부동소수점 숫자
부동소수점 숫자는 `3.14159`, `0.1`, `-273.15`와 같이 분수 요소가 있는 숫자입니다.
부동소수점 타입은 정수 타입보다 훨씬 넓은 범위의 값을 나타낼 수 있으며, `Int`가 저장할 수 있는 것 보다 훨씬 크거나 작은 값을 저장할 수 있습니다. 스위프트는 두 개의 부호가 있는 부동소수점 숫자 타입을 제공합니다 :
- `Double`은 64비트의 부동소수점 숫자를 나타냅니다.
- `Float`는 32비트의 부동소수점 숫자를 나타냅니다.
> 노트  
> `Float`의 정확도가 6개의 소수점 숫자만큼 작은 반면,  `Double`의 정확도는 최소 15개의 소수점 숫자를 가집니다. 사용할 적절한 부동소수점 타입은 코드에서 다뤄야 할 필요가 있는 값의 범위에 따라 달라집니다. 두 특성이 모두 적절할 수 있는 상황에서는, `Double`이 선호됩니다.  

## Type Safety and Type Inference
스위프트는 *타입-안전* 언어입니다. 타입 안전 언어는 당신의 코드가 다루는 값의 타입이 명확해지도록 장려합니다. 만약 당신의 코드 일부가 String을 요구한다면, 그것에 실수로라도 Int를 전달할 수 없습니다.
스위프트가 타입 안전 언어이기 때문에, 코드를 컴파일할 때 *타입 체크*를 수행하며 일치하지 않는 타입은 에러로 표시합니다. 이것은 개발 프로세스에서 당신이 에러를 가능한 일찍 찾아내고 고칠 수 있도록 합니다.
타입 체크는 서로 다른 타입의 값을 다룰 때 에러를 피하도록 도와줍니다. 하지만, 이것은 당신이 선언하는 모든 상수와 변수의 타입을 명시해야 한다는 뜻은 아닙니다. 만약 필요한 값의 타입을 명시하지 않는다면, 스위프트는 적절한 타입을 계산하기 위해 *타입 추론*을 사용합니다. 타입 추론은 컴파일러가 당신의 코드를 컴파일할 때, 당신이 제공한 값을 간단히 검사함으로써 특정 표현의 타입을 자동으로 추론하도록 해 줍니다.

타입 추론 덕분에, 스위프트는 C언어나 Objective-C같은 언어보다 타입 선언을 훨씬 적게 요구합니다. 상수와 변수는 여전히 명시적으로 타입이 지정되어야 하지만, 타입을 특정해야 하는 작업의 대부분은 당신을 위해 작업이 완료됩니다.
타입 추론은 초기값이 있는 상수나 변수를 선언할 때 특히 유용합니다. 이것은 상수나 변수를 선언하는 시점에 리터럴 값 (또는 리터럴)을 할당함으로서 종종 수행됩니다. (리터럴 값은 아래 예시의 `42` 나 `3.14159` 처럼 소스 코드에 직접 나타난 값을 말합니다.)
예를 들어, 만약 새로운 상수에 42라는 리터럴 값을 할당하며 그것이 어떤 타입인지 지정하지 않으면, 스위프트는 당신이 그 상수가 Int가 되길 원했을 것이라고 추론합니다. 왜냐하면 당신이 정수형처럼 보이는 숫자로 그 상수를 초기화했기 때문입니다 :
``` swift
let meaningOfLife = 42
// meaningOfLife는 Int타입으로 추론됩니다.
```
마찬가지로, 만약 당신이 부동소수점 리터럴에 타입을 특정하지 않는다면, 스위프트는 당신이 Double을 만들고 싶었을 것이라고 추론합니다 :
``` swift
let pi = 3.14159
// pi는 Double타입으로 추론됩니다.
```
스위프트는 부동소수점 숫자의 타입을 추론할 때 (Float보다는) 항상 Double을 선택합니다.
만약 당신이 정수와 부동소수점 숫자를 조합해 표현한다면, 그 구문으로부터 Double 타입이 추론될 것입니다 :
``` swift
let anotherPi = 3 + 0.14159
// anotherPi 역시 Double타입으로 추론됩니다.
```
3이라는 리터럴 값은 그 자체로 명시된 타입이 없고, 그렇기 때문에 적절한 타입 추론 결과는 더해진 부분으로서의 부동소수점 리터럴의 존재로부터 Double이 됩니다.
- - - -
      
## 단어 정리
- fractional 분수의. 아주 적은
- precision 정확(성), 정밀(성)
	- precisely 정확하게.
- nature *특성. 본성.
- encourage 격려하다. 장려하다.
- flag (동사) 표시를 하다
- literal 문자 그대로의. (컴) 리터럴. 상수에 넣는 변하지 않는 데이터의 값
	- 상수는 변하지 않는 변수(메모리 위치)
	- 리터럴은 변하지 않는 변수의 데이터 값(메모리 위치 안의 값)
- combine 결합하다
- presence 있음. 존재함.
- decimal (형) 십진법의, (명) 소수
	- decimal point 소수점
- digit 숫자
- mismatched 일치하지 않는
- work out -를 계산하다
- deduce 추론하다. 연역하다.
- particularly 특히. 특별히.
- be done 수행되다
- in and of itself 그 자체로. 그것 자체는.