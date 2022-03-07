# Numeric Type Conversion
Use the Int type for all general-purpose integer constants and variables in your code, even if they’re known to be nonnegative. 
당신의 코드에서 모든 일반적인 목적의 인티저 변수 그리고 상수를 위해 인티저 타입을 사용해라 심지어 그들이 음수가 아닌걸 알더라도

Using the default integer type in everyday situations means that integer constants and variables are immediately interoperable in your code and will match the inferred type for integer literal values.
모든 상황에서 기본 인티저 타입을 사용한다는 건 인티저 상수 그리고 변수가 즉시 상호 운용 가능하고 정수 리터럴 값에 대해 추론된 유형과 일치함을 의미한다.

Use other integer types only when they’re specifically needed for the task at hand, because of explicitly sized data from an external source, or for performance, memory usage, or other necessary optimization. 
 뒤에서 부터 해석하기
외부로 소스로 부터 명시적인 규격화 된 데이터 또는 성능을 위해 메모리 사용 또는 다른 필수적인 최적화가 필요할 경우, 당면한 작업에 특별히 필요한 필요한 경우에만 다른 인티저 타입을 사용하세요  

Using explicitly sized types in these situations helps to catch any accidental value overflows and implicitly documents the nature of the data being used.
이러한 상황에서 명시적 크기가 지정된 유형을 사용하면 우발적인 오버플로우를 잡거나 그리고 데이터의 특성을 암시적으로 문서화하는데 도움이 된다.



interoperable: 상호 운용 가능한
for the task at hand: 당면한 과제를 위해
any accidental  : 우발적인, 뜻밖의
nature: 특성