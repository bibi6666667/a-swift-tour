Use `if` and `switch` to make conditionals, and use `for`-`in`, `while`, and `repeat`-`while` to make loops.

if, switch는 조건문을 만들 때, for-in, while 그리고 repeat -while은 루프를 만들 때 사용해라.



Parentheses around the condition or loop variable are optional. Braces around the body are required.

조건 또는 루프 변수를 감싸는 괄호는 옵셔널이다. 바디를 감싸는 중괄호는 필수이다.



In an `if` statement, the conditional must be a Boolean expression—this means that code such as `if score { ... }` is an error, not an implicit comparison to zero.

하나의 if문에서 조건은 불린 표현식이여만 한다. 즉  `if score { ... }` 는 에러이다. 암시적인 비교가 아니다 영이랑



You can use `if` and `let` together to work with values that might be missing. 

might be missing ??

if와 let을 같이 사용하면 값이 동작할 수 있다. 잃어버렸을 지라도.



These values are represented as optionals. 

이값들은 옵셔널로 표현된다.



An optional value either contains a value or contains `nil` to indicate that a value is missing.

옵셔널은 값 또는 빈값을 갖는다. 

nil은 값이 사라진걸 가르킨다.

nil은 값이 사라진걸 의미한다.



Write a question mark (`?`) after the type of a value to mark the value as optional.

값 타입 뒤에 ?를 작성하면 그 값은 옵셔널이다.



Change `optionalName` to `nil`. What greeting do you get? 

optionalName을 닐로 바꾸면 어떤 문구가 나오니? 



Add an `else` clause that sets a different greeting if `optionalName` is `nil`.

???



If the optional value is `nil`, the conditional is `false` and the code in braces is skipped. 

만약 옵셔널 값이 닐이면, 조건문은 틀림이고 중괄호 안에있는 코드는 생략될것이다.



Otherwise, the optional value is unwrapped and assigned to the constant after `let`, which makes the unwrapped value available inside the block of code.

달리 옵셔널 값이 벗겨지고 그리고 let 상수에게 할당될것이다. 이것은 코드의 블록 내부에서 벗겨진 값을 사용할 수 있게 해준다.



Another way to handle optional values is to provide a default value using the `??` operator.

옵셔널 값을 핸들링하는 다른 방법은 ??연산자를 사용해서 기본값을 제공하는 것이다. 



 If the optional value is missing, the default value is used instead.

만약 옵셔널 값이 없다면, 기본값이 대신해서 사용될것이다.



Switches support any kind of data and a wide variety of comparison operations—they aren’t limited to integers and tests for equality.

스위치문은 어떤 종류의 데이터 그리고 다양한 비교를 지원하는 연산문이다. 스위치문은 인티저 그리고 테스트 비교에 제한되지 않는다.



Try removing the default case. What error do you get?

기본 케이스를 지우면, 어떤 에러를 볼 수 있니?



Braces: 중괄호

Clause: 절 (주절)