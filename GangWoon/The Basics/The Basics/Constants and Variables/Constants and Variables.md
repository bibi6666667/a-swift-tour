# Constants and Variables

Constants and variables associate a name (such as `maximumNumberOfLoginAttempts` or `welcomeMessage`) with a value of a particular type (such as the number `10` or the string `"Hello"`).

상수와 변수는이름과 연관된다값의 특유한 타입과 함께

상수와 변수는 이름을 특정 유형의 타입과 연결한다.



The value of a *constant* can’t be changed once it’s set, whereas a *variable* can be set to a different value in the future.

상수의 값은 변할 수 없다 한번 셋된 후, 반대로 변수는 미래에 다른 값으로 셋될 수 있다.



## Declaring Constants and Variables

Constants and variables must be declared before they’re used.

상수와 변수는 사용되기전에 선언되어야합니다.



You declare constants with the `let` keyword and variables with the `var` keyword.

상수는 키워드를 변수는 키워드를 사용해서 선언합니다.



Here’s an example of how constants and variables can be used to track the number of login attempts a user has made:

상수 그리고 변수가 유저가 만든 로그인 시도 숫자를 어떻게 추적하는지에 대한 예시가 있습니다.



This code can be read as:

이 코드는 이렇게 읽힙니다.



“Declare a new constant called `maximumNumberOfLoginAttempts`, and give it a value of `10`. 

키워드로 불리는 새로운 상수를 선언한다 그리고 10의 값을ㅈ ㅜㄴ다.



Then, declare a new variable called `currentLoginAttempt`, and give it an initial value of `0`.”

그 때, 새로운 변수 키워드를 선언하고 그리고 초기화 값으로 0을 준다.



In this example, the maximum number of allowed login attempts is declared as a constant, because the maximum value never changes.

예시에서 허용된 로그인 시도의 최대 숫자는 상수로 선언되었다. 왜냐하면 그 최대값은 변하지 않기 때문이다.



The current login attempt counter is declared as a variable, because this value must be incremented after each failed login attempt.

현재 로그인 숫자는 변수로 선언되었다. 그 이유는 값은 로그인 시도 실패후 증가해야하기 때문이다.



You can declare multiple constants or multiple variables on a single line, separated by commas:

여러개의 상수 또는 변수를 콤마로 분리된 단일 라인으로 선언할 수 있다.



If a stored value in your code won’t change, always declare it as a constant with the `let` keyword. 

당신의 코드에 저장값이 변경되길 원하지 않느다면 항상 상수 키워들 사용해서 선언하십시오.



Use variables only for storing values that need to be able to change.

변수는 변경할 수 있어야하는 값을 저장할 때 사용하세요 



particular: 특유한 개인의

associate: 연결지어 생각하다

once it’s set: 일단 설정되면

Then: 그 때 (과거 미래 둘다 사용가능)