## Generics



Write a name inside angle brackets to make a generic function or type.

제네릭 함수 또는 타입을 만들기 위해서 꺽쇠괄호 안에 이름을 작성하세요.



You can make generic forms of functions and methods, as well as classes, enumerations, and structures.

당신은 함수와 메소드의 제네릭 형태를 만들 수 있습니다. 알다싶이 클래스 열거형 그리고 구조체



Use `where` right before the body to specify a list of requirements—

요구사항의 리스트를 명시하기 위해서 바디 바로 전에 해당 키워드를 사용하세요.



for example, to require the type to implement a protocol, to require two types to be the same, or to require a class to have a particular superclass.

예를 들어서, 그 타입이 프로토콜을 구현하거나, 그 두 타입이 동일하거나, 클래스가 특정 부모클래스를 상속받는 걸 요구하려면



Modify the `anyCommonElements(_:_:)` function to make a function that returns an array of the elements that any two sequences have in common.

해당 메소드를 변경해라 요소의 배열을 리턴하도록 어떤 두 시퀀스가 갖는 공통점에 대해서



Writing `<T: Equatable>` is the same as writing `<T> ... where T: Equatable`.

두가지는 동일하다.