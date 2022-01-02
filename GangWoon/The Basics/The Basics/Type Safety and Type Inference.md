# Type Safety and Type Inference
Swift is a _type-safe_ language. 
스위프트는 타입 안전 언어이다.

A type safe language encourages you to be clear about the types of values your code can work with. 
타입 안전언어는 당신의 코드가 작동할 수있도록 값의 타입을 명확하게하기 권장한다.

If part of your code requires a String, you can’t pass it an Int by mistake.
만약 당신의 코드가 스트링을 요구하는데 인티저를 실수로 패스하지않도록

Because Swift is type safe, it performs _type checks_ when compiling your code and flags any mismatched types as errors. 
왜냐하면 스위프트는 타입안전 언어이기 때문에 이것은 타입체크를 수행한다. 당신의 코드를 컴파일링할때 그리고 잘못 매치된 타입에 에러를 표시한다.

This enables you to catch and fix errors as early as possible in the development process.
이것은 에러를 개발과정중에 알아차리고 고칠 수 있도록한다.

Type-checking helps you avoid errors when you’re working with different types of values. 
타입 체크는 도와준다 당신이 에러를 피하도록 값의 다른 타입을 작성할때

However, this doesn’t mean that you have to specify the type of every constant and variable that you declare. 
그러나 이말이 당신이 모든 상수나 변수를 선언할때 타입을 명시해야한다는 건 아니다.

If you don’t specify the type of value you need, Swift uses _type inference_ to work out the appropriate type. 
만약 당신이 필요로하는 값의 타입을 명식하지 않는다면 스위프트는 타입추론으로 적절한 타입을 작성할것이다.

Type inference enables a compiler to deduce the type of a particular expression automatically when it compiles your code, simply by examining the values you provide.
타입추론은  간단하게 당신이 제공하는 값을 검사하면서 당신의 코드가 컴파일 될 때 자동적으로 부분적인 표현식의 타입을  컴파일러가 추론할 수 있도록 한다.

Because of type inference, Swift requires far fewer type declarations than languages such as C or Objective-C. 
타입추론 때문에 스위프트는 씨나 옵젝씨 보다 적은 타입 선언을 요구된다.

Constants and variables are still explicitly typed, but much of the work of specifying their type is done for you.
상수 그리고 변수는 명시적으로 타입된다 그러나 그들의 타입을 명시하는 일의 대부분은 당신을 위해서 작성된다.

Type inference is particularly useful when you declare a constant or variable with an initial value. 
타입 추론은 특히 유용하다 상수나 변수를 초기화할때 

This is often done by assigning a _literal value_ (or _literal_) to the constant or variable at the point that you declare it. 
이것은 종종 선언하는 지점에서 상수나 변수를 리터럴 값을 할당한다.

(A literal value is a value that appears directly in your source code, such as 42 and 3.14159 in the examples below.)
예시코드 42그리고 3.14처럼 리터럴 값은 당신의 코드에 직접적으로 나타난다.

For example, if you assign a literal value of 42 to a new constant without saying what type it is, Swift infers that you want the constant to be an Int, because you have initialized it with a number that looks like an integer:
예를 들어서 만약 42 값의 리터럴을 새로운 상수에 타입을 말하지 않고 할당했다면 스위프트는상수가 인티저를 원한다고 추론할것이다. 왜나햐면 이티저로 보이는 숫자로 초기화 했기 때문이다.

encourages: 격려하다.
performs: 수행하다
appropriate: 적절한
deduce: 추론하다
examining: 검사
particularly: 특히
literal value: 리터럴 값
work out: 계산하다