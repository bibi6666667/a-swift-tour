# A Swift Tour - Protocols and Extensions

> Use `protocol` to declare a protocol.
>
> ``` swift
> protocol ExampleProtocol {
>     var simpleDescription: String { get }
>     mutating func adjust()
> }
> ```
>
> Classes, enumerations, and structs can all adopt protocols.
>
> ``` swift
> class SimpleClass: ExampleProtocol {
>     var simpleDescription: String = "A very simple class."
>     var anotherProperty: Int = 69105
>     func adjust() {
>         simpleDescription += "  Now 100% adjusted."
>     }
> }
> var a = SimpleClass()
> a.adjust()
> let aDescription = a.simpleDescription
> 
> struct SimpleStructure: ExampleProtocol {
>     var simpleDescription: String = "A simple structure"
>     mutating func adjust() {
>         simpleDescription += " (adjusted)"
>     }
> }
> var b = SimpleStructure()
> b.adjust()
> let bDescription = b.simpleDescription
> ```
>
> >  EXPERIMENT
> >
> > Add another requirement to `ExampleProtocol`. What changes do you need to make to `SimpleClass` and `SimpleStructure` so that they still conform to the protocol?
>
> Notice the use of the `mutating` keyword in the declaration of `SimpleStructure` to mark a method that modifies the structure. The declaration of `SimpleClass` doesn’t need any of its methods marked as mutating because methods on a class can always modify the class.
>
> Use `extension` to add functionality to an existing type, such as new methods and computed properties. You can use an extension to add protocol conformance to a type that’s declared elsewhere, or even to a type that you imported from a library or framework.
>
> ``` swift
> extension Int: ExampleProtocol {
>     var simpleDescription: String {
>         return "The number \(self)"
>     }
>     mutating func adjust() {
>         self += 42
>     }
> }
> print(7.simpleDescription)
> // Prints "The number 7"
> ```
>
> > EXPERIMENT
> >
> > Write an extension for the `Double` type that adds an `absoluteValue` property.
>
> You can use a protocol name just like any other named type—for example, to create a collection of objects that have different types but that all conform to a single protocol. When you work with values whose type is a protocol type, methods outside the protocol definition aren’t available.
>
> ``` swift
> let protocolValue: ExampleProtocol = a
> print(protocolValue.simpleDescription)
> // Prints "A very simple class.  Now 100% adjusted."
> // print(protocolValue.anotherProperty)  // Uncomment to see the error
> ```
>
> Even though the variable `protocolValue` has a runtime type of `SimpleClass`, the compiler treats it as the given type of `ExampleProtocol`. This means that you can’t accidentally access methods or properties that the class implements in addition to its protocol conformance.



## 프로토콜과 익스텐션

프로토콜을 선언하기 위해 `protocol`을 사용하십시오.

``` swift
protocol ExampleProtocol {
    var simpleDescription: String { get }
    mutating func adjust()
}
```

클래스, 열거형, 구조체 모두가 프로토콜을 채택할 수 있습니다.

``` swift
class SimpleClass: ExampleProtocol {
    var simpleDescription: String = "A very simple class."
    var anotherProperty: Int = 69105
    func adjust() {
        simpleDescription += "  Now 100% adjusted."
    }
}
var a = SimpleClass()
a.adjust()
let aDescription = a.simpleDescription

struct SimpleStructure: ExampleProtocol {
    var simpleDescription: String = "A simple structure"
    mutating func adjust() {
        simpleDescription += " (adjusted)"
    }
}
var b = SimpleStructure()
b.adjust()
let bDescription = b.simpleDescription
```

> 실험
>
> `ExampleProtocol`에 또다른 요건을 추가하십시오. 여전히 프로토콜을 따르기 위해 `SimpleClass` 와 `SimpleStructure`를 만들 때 어떤 변화가 필요합니까?

`SimpleStructure`의 선언에 구조체를 수정하는 메서드를 표시하기 위해 `mutating`키워드를 사용한 것을 주목하십시오. `SimpleClass`선언의 메서드에는 mutating과 같은 어떤 표시도 필요하지 않습니다. 왜냐하면 클래스의 메서드는 항상 그 클래스를 수정하기 때문입니다.

존재하는 타입에 새로운 메서드나 연산 프로퍼티와 같은 기능을 추가하기 위해 `extension`을 사용하십시오. 다른 곳에서 선언되었거나 라이브러리 또는 프레임워크에서 불러온 타입에 프로토콜 일치를 추가하기 위해 익스텐션을 사용할 수 있습니다.

``` swift
extension Int: ExampleProtocol {
    var simpleDescription: String {
        return "The number \(self)"
    }
    mutating func adjust() {
        self += 42
    }
}
print(7.simpleDescription)
// Prints "The number 7"
```

> 실험
>
> Double타입에 absoluteValue 프로퍼티를 추가하는 익스텐션을 작성해 보십시오.

다른 이름 있는 타입들과 마찬가지로 프로토콜 이름을 사용할 수 있습니다. 예를 들어, 한 프로토콜을 따르지만 다른 타입들을 가진 객체들의 컬렉션을 만들기 위해서 프로토콜 이름을 사용할 수 있습니다. 타입이 프로토콜 타입인 값을 다룰 때는, 프로토콜 밖의 메서드 선언은 사용할 수 없습니다.

``` swift
let protocolValue: ExampleProtocol = a
print(protocolValue.simpleDescription)
// Prints "A very simple class.  Now 100% adjusted."
// print(protocolValue.anotherProperty)  // Uncomment to see the error

// 프로토콜 타입인 값으로 프로토콜 자체를 넣을 순 없고, 그 프로토콜을 채택한 객체가 올 수 있다.
// ExampleProtocol을 준수했다면 a 대신 다른 대상도 할당될 수 있다.
// 하지만 protocolValue는 ExampleProtocol타입이기 때문에 프로토콜에 정의된 요건들만 사용할 수 있다.
```

변수 `protocolValue` 가 실행 시점에 `SimpleClass` 타입을 가짐에도 불구하고, 컴파일러는 그것을 `ExampleProtocol`의 정해진 타입으로 다룹니다. 이것은 당신이 우연히라도 프로토콜 요건 외에 클래스가 구현한 메서드나 프로퍼티에 접근할 수 없음을 의미합니다.



## 단어 정리

- extension 확대 (컴) 익스텐션
- adopt 입양하다 (컴) 채택하다
- requirement 필요(조건). 요건
- modify 수정하다
- functionality 기능성. 기능.
- computed property (컴) 연산 프로퍼티
- conformance 일치. 부합. 적합
- conform 따르다. 순응하다. 준수하다.
- elsewhere 다른 곳에서
- given 정해진. 특정한.