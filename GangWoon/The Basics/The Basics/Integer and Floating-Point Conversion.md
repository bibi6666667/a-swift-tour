Integer and Floating-Point Conversion

Conversions between integer and floating-point numeric types must be made explicit:

인티저 그리고 소수점 뉴메릭 타입의 변환은 명시적으로 만들어야합니다.



Here, the value of the constant `three` is used to create a new value of type `Double`, so that both sides of the addition are of the same type. 

"삼" 상수의 값은 새로운 더블타입 값을 만드는데 사용된다. 그래서 더하기 양변은 같은 타입이다.



Without this conversion in place, the addition would not be allowed.

이 변환이 없다면 덧셈은 허락되지 않을 겁니다.



Floating-point to integer conversion must also be made explicit. 

소수점에서 인티저 변환은 명시적이야만 합니다.



An integer type can be initialized with a `Double` or `Float` value:

인티저 타입은 더블이나 플로트로 생성될 수 있습니다.



Floating-point values are always truncated when used to initialize a new integer value in this way. 

새로운 정수를 다음과 같이 초기화하면, 소수점은 값은 항상 잘릴것 입니다.



This means that `4.75` becomes `4`, and `-3.9` becomes `-3`.

4.75는 4 그리고 -3.9는 -3이 되는걸 의미합니다.



The rules for combining numeric constants and variables are different from the rules for numeric literals. 

뉴메릭 상수 그리고 변수를 합치는 룰은 뉴메릭 리터럴과 다르다 



The literal value `3` can be added directly to the literal value `0.14159`, because number literals don’t have an explicit type in and of themselves. 

리터럴 값 3은 리터럴 값 0.14와 직접적으로 더할 수 있다, 그 이유는 리터럴 숫자는 명시적인 타입이 없기 때문이다.



Their type is inferred only at the point that they’re evaluated by the compiler.

그들의 타입은 그들이 컴파일러에 평가되어지는 시점에 추론되어진다.