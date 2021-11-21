# Objects and Classes

Use `class` followed by the class’s name to create a class.

class 뒤에 이름을 붙여서 클래스를 생성할 수 있다.



A property declaration in a class is written the same way as a constant or variable declaration, except that it’s in the context of a class.

클래스에서 프로퍼티 선언은 상수 또는 변수 선언과 동일하다. 클래스 내부에 있는 걸 제외하면



Likewise, method and function declarations are written the same way.

메소드와 함수 선언도 동일하다



Add a constant property with `let`, and add another method that takes an argument.

let을 사용해서 상수 프로퍼티를 추가하고, 아규먼트를 갖는 메소드를 추가해라.



Create an instance of a class by putting parentheses after the class name.

클래스 인스턴스를 생성해라 클래스 이름뒤에 괄호를 사용해서



Use dot syntax to access the properties and methods of the instance.

인스턴스의 속성과 메소드를 접근할 수 있다. 닷을 사용해서



This version of the `Shape` class is missing something important: an initializer to set up the class when an instance is created. 

모형의 클래스는 중요한 것을 잃어버렸다. 초기화로 클래스를 셋업한다 인스턴스가 생성될 때



Use `init` to create one.

초기화를 사용해서 하나를 생성해라.



Notice how `self` is used to distinguish the `name` property from the `name` argument to the initializer.

self로 속성 이름을 구분할 때 사용한다 아규먼트 이름과  구분하기 위해 초기화에서



The arguments to the initializer are passed like a function call when you create an instance of the class. 

초기화의 아규먼트는 함수 호출처럼 전달된다. 클래스의 인스턴스를 생성할 떄



Every property needs a value assigned—either in its declaration (as with `numberOfSides`) or in the initializer (as with `name`).

모든 프로퍼티는 값이 할당되어야한다. 선언될 떄, 초기화될 때



Use `deinit` to create a deinitializer if you need to perform some cleanup before the object is deallocated.

디이닛을 사용해서 해제자를 생성할 수 있따. 객체가 디이닛되기전에 청소할 게 필요하다면



Subclasses include their superclass name after their class name, separated by a colon. 

상속은 그들의 부모 이름을 그들의 이름 전에 포함시킨다 콜론을 사용해서 분리된다.



There’s no requirement for classes to subclass any standard root class, so you can include or omit a superclass as needed.

클래스에게 요구사항은 없다 상속받기 위해 어떤 루트 클래스를, 너는 부모 클래스를 포함시키거나 생략할 수 있다 필요에 따라서



Methods (on a subclass that override the superclass’s implementation) are marked with `override`—

메소드 오버라이드로 지정된다. 상속받은 부모 클래스의 구현을 오버라이드하는



overriding a method by accident, without `override`, is detected by the compiler as an error. 

우연히 메소드를 오버라이드하면 신텍스 없이, 컴파일러가 에러를 발견해줄거다.



The compiler also detects methods with `override` that don’t actually override any method in the superclass.

또한 부모클래스에서 오버라이드가 필요하지 않는 메소드도 발견해준다.



Make another subclass of `NamedShape` called `Circle` that takes a radius and a name as arguments to its initializer. 

원이 네임드 쉐잎을 상속 받고. 반지름과 이름을 아규먼트로 받는 초기화를 만들어라



Implement an `area()` and a `simpleDescription()` method on the `Circle` class.

영역과 간단한 설명 메소드를 원 클래스에 구현해라.



In addition to simple properties that are stored, properties can have a getter and a setter.

추가적으로 간단한 프로퍼티는 저장된다. 게터와 세터할 수 있다.



In the setter for `perimeter`, the new value has the implicit name `newValue`.

perimeter의 세터에서 새로운 값은 암묵적으로 newValue이다. 



You can provide an explicit name in parentheses after `set`.

set 뒤에 명시적으로 이름을 제공할 수 있다.



Notice that the initializer for the `EquilateralTriangle` class has three different steps:

정삼각형 초기화는 세가지 다른 단계가 있다.



1. Setting the value of properties that the subclass declares.

상속에서 선언된 프로퍼티 값을 셋팅한다.



2. Calling the superclass’s initializer.

부모 클래스의 초기화를 호출한다



3. Changing the value of properties defined by the superclass.

부모 클래스의 선언된 프로퍼티의 값을 변경한다.



4. ### Any additional setup work that uses methods, getters, or setters can also be done at this point. ???

어떤 추가적인 셋업이 작동한다. 메소드를 사용하거나 게터 또는 세터는 이 시점부터 작동한다.



If you don’t need to compute the property but still need to provide code that’s run before and after setting a new value, use `willSet` and `didSet`.

속성을 계산할 필요가 없다면 하지만 여전히 코드를 새로운 값이 셋팅되기 전이나 후에 코드를 제공해야한다면, willSet, didSet을 사용해라



### The code (you provide) is run any time the value changes (outside of an initializer.)  ???

초기화 밖에서 모든 값의 변경에 대해서 제공해줄거다



For example, the class below ensures that the side length of its triangle is always the same as the side length of its square.

예를 들어서 아래 클래스는 보증한다. 삼각형의 변은 항상 정사각형의 변과 동일하다.



When working with optional values, you can write `?` before operations like methods, properties, and subscripting. 

옵셔널 값과 같이 일한다면, 메소드, 속성 서브크립트 뒤에 ?를 작성할 수 있다.



If the value before the `?` is `nil`, everything after the `?` is ignored and the value of the whole expression is `nil`.

만약 ?이전의 값이 nil이라면 ?이후의 모든 것은 무시된다. 그리고 그 값의 전체 표현은 nil이 된다.



### Otherwise, the optional value is unwrapped, and everything after the `?` acts on the unwrapped value.  ???

다르게, 옵셔널값이 벗겨졌다면, ? 이후에 값들은 벗겨진 상태로 행동한다.



### In both cases, the value of the whole expression is an optional value. ???

모든 케이스에서 모든 표현식의 값은 옵셔널 값이다.



---

Likewise: 유사하게

accident: 우연히, 사고

below: 낮은