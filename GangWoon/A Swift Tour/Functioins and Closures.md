

Use `func` to declare a function.

Func를 선언해서 함수를 사용한다.



 Call a function by following its name with a list of arguments in parentheses.

호출해라 함수를 이름과 괄호 안에있는 아규먼트 리스트와 함께



 Use `->` to separate the parameter names and types from the function’s return type.

파라미터 이름과 타입을 분리하기 위해서  ->를 사용해서, 함수의 리턴타입으로부터



Remove the `day` parameter. Add a parameter to include today’s lunch special in the greeting.

day 파라미터를 지워라. 오늘의 점심 스페셜을 추가해라.



By default, functions use their parameter names as labels for their arguments.

기본적으로 함수는 그들의 라벨 이름으로 파라미터를 사용한다. 그들의 아규먼트를 위해서



Write a custom argument label before the parameter name, or write `_` to use no argument label.

파라미터 이름전에 커스텀 레이블을 작성해라 또는 아규먼트가 없애기 위해 _ 를 작성해라



Use a tuple to make a compound value—for example, to return multiple values from a function.

합성된 값을 만들려면 튜플을 사용해라, 예를 들어서 다수의 값을 리턴하는 함수를 만들 때



 The elements of a tuple can be referred to either by name or by number.

튜플의 값은 추론되어진다 이름 혹은 숫자로



Functions can be nested. 

함수는 지역일 수 있다.



Nested functions have access to variables that were declared in the outer function.

지역함수는 접근한다. 변경하기 위해서, 지역함수는 선언되어진다 다른 함수에서



You can use nested functions to organize the code in a function that’s long or complex.

지역함수를  함수 안에서 정의할 수 있다. 그 함수가 길고 복잡하다면.



Functions are a first-class type.

함수는 일급시민 타입이다. 



This means that a function can return another function as its value.

함수가 다른 함수를 값으로 리턴할 수 있다는 걸 의미한다.



A function can take another function as one of its arguments.

함수의 하나의 아규먼트로 다른 함수를 사용할 수 있다.



Functions are actually a special case of closures: blocks of code that can be called later.

함수는 사실 특별한 케이스의 클로저이다. (코드의 블럭이라고 불렸다.)



The code (in a closure) has access to things like variables and functions 

클로저 내부에 있는 코드는 변수나 함수를 접근할 수 있다.



that(closure) were available in the scope where the closure was created,

범위 내부에서 가능하다. 클로저가 생성된 곳에서



 even if the closure is in a different scope when it’s executed

심지어 클로저가 다른 스코프(시간)에 실행되더라도



you saw an example of this already with nested functions. 

당신은 이것의 예시를 봤었다 지역 함수에서



You can write a closure without a name by surrounding code with braces (`{}`). 

클로저를 이름없이 소괄호를 사용해서 사용할 수 있다.



You have several options for writing closures more concisely.

클로저를 더 간소하게 사용할 수 있는 몇가지 옵션이 있습니다.



When a closure’s type is already known, such as the callback for a delegate, you can omit the type of its parameters, its return type, or both. 

클로저 타입을 미리 알 수 있을 때, 델리게이트로 부터오는 콜백과 같이 너는 생략할 수 있다 파라미터의 타입, 리턴 타입 또는 둘다



Single statement closures implicitly return the value of their only statement.



Use `in` to separate the arguments and return type from the body.

in 을 사용해서 아규먼트와 리턴 타입을 나눌 수 있다 바디로부터



You can refer to parameters by number instead of by name—this approach is especially useful in very short closures.

파라미터를 추론할 수 있따 이름대신에 숫자를 사용해서- 해당 접근법은 아주 짧은 클로저에서 특별히 유용하다.



A closure passed as the last argument to a function can appear immediately after the parentheses.

클로저가 함수의 마지막 아규먼트로 전달된다면 괄호 후에 즉시 나타난다.



When a closure is the only argument to a function, you can omit the parentheses entirely.

함수의 아규먼트가 오직 클로저라면 당신은 괄호를 생략할 수 있다.



compound: 합성의

organize: 정리하다, 체계화하다

concisely: 간소하게