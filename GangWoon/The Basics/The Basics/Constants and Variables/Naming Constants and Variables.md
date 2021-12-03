### Naming Constants and Variables

Constant and variable names can contain almost any character, including Unicode characters:

상수 그리고 변수 이름은 유니 코드 캐릭터를 포함해서 대부분 캐릭터도 포함할 수 있다.



Constant and variable names can’t contain whitespace characters, mathematical symbols, arrows, private-use Unicode scalar values, or line- and box-drawing characters. 

상수 그리고 변수는 공백 문자, 수학적 심볼, 화살표, 프라이빗하게 사용되는 유니코드 스칼라 값 또는 라인 그리고 박스를 그리는 캐리턱를 포함할 수 없다



Nor can they begin with a number, although numbers may be included elsewhere within the name.

뿐만 아니라 숫자로 시작할 수 없다 비록 숫자들이 그들의 이름 내부 어디서든 포함될 수 있다.



Once you’ve declared a constant or variable of a certain type, you can’t declare it again with the same name, or change it to store values of a different type. 

어떤 타입의 상수 또는 변수를선언되어질 때, 같은 이름으로 다시 선언할 수 없다. 또는 다른 타입의 값으로 저장하기 위해 변경할 수 없다.



Nor can you change a constant into a variable or a variable into a constant.

상수를 변수로 변경하거나 또는 변수를 상수로 변경할 수 없다.



If you need to give a constant or variable the same name as a reserved Swift keyword, surround the keyword with backticks (```) when using it as a name. 

만약 상수 또는 변수를 동일한 예약된 스위프트 키워드를 사용하고 싶다면 이름 사용할 때 키워드를 백틱으로 감싸주세요.



However, avoid using keywords as names unless you have absolutely no choice.

그러나 선택의 여지가 없는 경우가 아니면, 키워드를 이름으로 사용하는 건 피하세요 





You can change the value of an existing variable to another value of a compatible type. 

호환 가능한 타입의 다른 값으로 존재하는 값으로 변경할 수 있다.



In this example, the value of `friendlyWelcome` is changed from `"Hello!"` to `"Bonjour!"`:

예를 들어서 키워드 값이 헬로에서 봉쥬르로 변경되었다.



Unlike a variable, the value of a constant can’t be changed after it’s set. 

변수와 달리 상수값은 셋된 이후에 변경될 수 없다.



Attempting to do so is reported as an error when your code is compiled:

이걸 시도한다면 당신의 코드가 컴파일될 때 에러가 리포트 될것이다.



backticks: 백틱

unless: 뭐뭐 하지 않는 한

compatible: