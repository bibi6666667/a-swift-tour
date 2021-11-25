## Protocols and Extensions



Use `protocol` to declare a protocol.

프로토콜을 선언하기 위해서 해당 키워드를 사용해라.



Classes, enumerations, and structs can all adopt protocols.

클래스 열거형 구조체 모두 프로토콜을 준수할 수 있다.



Add another requirement to `ExampleProtocol`. 

해당 프로토콜을 추가적으로 채택하도록 추가해라.



What changes do you need to make to `SimpleClass`and `SimpleStructure` so that they still conform to the protocol?

어떤 변화가 필요로 하게 만드는가 클래스와 구조체에서 그리고 그들은 여전히 프로토콜을 준수하고 있는가



Notice the use of the `mutating` keyword in the declaration of `SimpleStructure` to mark a method that modifies the structure. 

주목하라 키워드의 사용을 구조체 내부에서 선언을 메소드가 해당 구조체를 변경할 수 있도록 만드는 걸



The declaration of `SimpleClass` doesn’t need any of its methods marked as mutating because methods on a class can always modify the class.

클래스 선언에서는  클래스가 클래스를 변경하는 메소드는 해당 키워드로 표시될 필요가 없다. 



Use `extension` to add functionality to an existing type, such as new methods and computed properties. 

새로운 메소드나 컴퓨티트 프로퍼티를 존재하는 타입에 기능적으로 추가할 수 있다. 해당 키워드를 사용해서



You can use an extension to add protocol conformance to a type that’s declared elsewhere, or even to a type that you imported from a library or framework.

당신은 확장을 프로토콜을 준수하도록 사용할 수 있다. 타입이 선언된 어디에서나 또는 라이브러리나 프레임워크로 부터 임포트 받은 타입도 가능하다.



Write an extension for the `Double` type that adds an `absoluteValue` property.

더블 타입에 절대값 속성을 작성하라.



You can use a protocol name just like any other named type—

프로토콜 이름을 다름 타입처럼 작성할 수 있다.



for example, to create a collection of objects that have different types but that all conform to a single protocol. 

예를 들어서 객체의 컬랙션을 생성할 때 그들은 다른 타입이지만 하나의 프로토콜을 준수한다.



When you work with values whose type is a protocol type, methods outside the protocol definition aren’t available. ???



Even though the variable `protocolValue` has a runtime type of `SimpleClass`, the compiler treats it as the given type of `ExampleProtocol`. 

심지어 해당 값의 런타입 값은 심플클래스이다. 컴파일러는 이 값을 프로토콜로 다룬다.



This means that you can’t accidentally access methods or properties that the class implements in addition to its protocol conformance.

???



functionality: 기능성

conformance: 일치

accidentally: 우연히