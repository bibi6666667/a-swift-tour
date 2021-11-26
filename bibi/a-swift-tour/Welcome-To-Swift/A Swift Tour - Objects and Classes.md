# A Swift Tour - Objects and Classes

> ## Objects and Classes
>
> Use `class` followed by the class’s name to create a class. A property declaration in a class is written the same way as a constant or variable declaration, except that it’s in the context of a class. Likewise, method and function declarations are written the same way.
>
> ``` swift
> class Shape {
>     var numberOfSides = 0
>     func simpleDescription() -> String {
>         return "A shape with \(numberOfSides) sides."
>     }
> }
> ```
>
> > EXPERIMENT
> >
> > Add a constant property with `let`, and add another method that takes an argument.
>
> Create an instance of a class by putting parentheses after the class name. Use dot syntax to access the properties and methods of the instance.
>
> ``` swift
> var shape = Shape()
> shape.numberOfSides = 7
> var shapeDescription = shape.simpleDescription()
> ```
>
> This version of the `Shape` class is missing something important: an initializer to set up the class when an instance is created. Use `init` to create one.
>
> ``` swift
> class NamedShape {
>     var numberOfSides: Int = 0
>     var name: String
> 
>     init(name: String) {
>         self.name = name
>     }
> 
>     func simpleDescription() -> String {
>         return "A shape with \(numberOfSides) sides."
>     }
> }
> ```
>
> Notice how `self` is used to distinguish the `name` property from the `name` argument to the initializer. The arguments to the initializer are passed like a function call when you create an instance of the class. Every property needs a value assigned—either in its declaration (as with `numberOfSides`) or in the initializer (as with `name`).
>
> Use `deinit` to create a deinitializer if you need to perform some cleanup before the object is deallocated.
>
> Subclasses include their superclass name after their class name, separated by a colon. There’s no requirement for classes to subclass any standard root class, so you can include or omit a superclass as needed.
>
> Methods on a subclass that override the superclass’s implementation are marked with `override`—overriding a method by accident, without `override`, is detected by the compiler as an error. The compiler also detects methods with `override` that don’t actually override any method in the superclass.
>
> ``` swift
> class Square: NamedShape {
>     var sideLength: Double
> 
>     init(sideLength: Double, name: String) {
>         self.sideLength = sideLength
>         super.init(name: name)
>         numberOfSides = 4
>     }
> 
>     func area() -> Double {
>         return sideLength * sideLength
>     }
> 
>     override func simpleDescription() -> String {
>         return "A square with sides of length \(sideLength)."
>     }
> }
> let test = Square(sideLength: 5.2, name: "my test square")
> test.area()
> test.simpleDescription()
> ```
>
> >  EXPERIMENT
> >
> > Make another subclass of `NamedShape` called `Circle` that takes a radius and a name as arguments to its initializer. Implement an `area()` and a `simpleDescription()` method on the `Circle` class.
>
> In addition to simple properties that are stored, properties can have a getter and a setter.
>
> ``` swift
> class EquilateralTriangle: NamedShape {
>     var sideLength: Double = 0.0
> 
>     init(sideLength: Double, name: String) {
>         self.sideLength = sideLength
>         super.init(name: name)
>         numberOfSides = 3
>     }
> 
>     var perimeter: Double {
>         get {
>             return 3.0 * sideLength
>         }
>         set {
>             sideLength = newValue / 3.0
>         }
>     }
> 
>     override func simpleDescription() -> String {
>         return "An equilateral triangle with sides of length \(sideLength)."
>     }
> }
> var triangle = EquilateralTriangle(sideLength: 3.1, name: "a triangle")
> print(triangle.perimeter)
> // Prints "9.3"
> triangle.perimeter = 9.9
> print(triangle.sideLength)
> // Prints "3.3000000000000003"
> ```
>
> In the setter for `perimeter`, the new value has the implicit name `newValue`. You can provide an explicit name in parentheses after `set`.
>
> Notice that the initializer for the `EquilateralTriangle` class has three different steps:
>
> 1. Setting the value of properties that the subclass declares.
> 2. Calling the superclass’s initializer.
> 3. Changing the value of properties defined by the superclass. Any additional setup work that uses methods, getters, or setters can also be done at this point.
>
> If you don’t need to compute the property but still need to provide code that’s run before and after setting a new value, use `willSet` and `didSet`. The code you provide is run any time the value changes outside of an initializer. For example, the class below ensures that the side length of its triangle is always the same as the side length of its square.
>
> ```swift
> class TriangleAndSquare {
>     var triangle: EquilateralTriangle {
>         willSet {
>             square.sideLength = newValue.sideLength
>         }
>     }
>     var square: Square {
>         willSet {
>             triangle.sideLength = newValue.sideLength
>         }
>     }
>     init(size: Double, name: String) {
>         square = Square(sideLength: size, name: name)
>         triangle = EquilateralTriangle(sideLength: size, name: name)
>     }
> }
> var triangleAndSquare = TriangleAndSquare(size: 10, name: "another test shape")
> print(triangleAndSquare.square.sideLength)
> // Prints "10.0"
> print(triangleAndSquare.triangle.sideLength)
> // Prints "10.0"
> triangleAndSquare.square = Square(sideLength: 50, name: "larger square")
> print(triangleAndSquare.triangle.sideLength)
> // Prints "50.0"
> ```
>
> When working with optional values, you can write `?` before operations like methods, properties, and subscripting. If the value before the `?` is `nil`, everything after the `?` is ignored and the value of the whole expression is `nil`. Otherwise, the optional value is unwrapped, and everything after the `?` acts on the unwrapped value. In both cases, the value of the whole expression is an optional value.
>
> ``` swift
> let optionalSquare: Square? = Square(sideLength: 2.5, name: "optional square")
> let sideLength = optionalSquare?.sideLength
> ```



## 객체와 클래스

클래스를 만들기 위해 `class`와 그 뒤에 클래스 이름을 사용하십시오. 클래스의 프로퍼티 선언은 클래스 맥락 안에 있다는 것만 제외하고는 상수나 변수 선언과 동일한 방식으로 작성됩니다. 비슷하게, 메서드와 함수 선언들도 동일한 방식으로 작성됩니다.

``` swift
class Shape {
    var numberOfSides = 0
    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```

> 실험
>
> `let` 으로 상수 프로퍼티를 추가하고, 전달인자를 받는 다른 메서드 하나를 추가해 보십시오.

클래스 이름 뒤에 소괄호를 붙임으로써 클래스의 인스턴스를 만드십시오. 인스턴스의 프로퍼티와 메서드에 접근하기 위해 점(`.`) 문법을 사용하십시오.

``` swift
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```

이 `Shape` 클래스의 버전은 어떤 중요한 것이 빠져 있습니다 : 그것은 인스턴스가 생성될 때 클래스를 준비하기 위한 생성자입니다. 생성자를 만들기 위해 `init`을 사용하십시오.

``` swift
class NamedShape {
    var numberOfSides: Int = 0
    var name: String

    init(name: String) {
        self.name = name
    }

    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```

`name` 프로퍼티와 생성자의 `name` 전달인자를 구별하기 위해 `self` 가 어떻게 사용되었는지에 주목하십시오. 클래스의 인스턴스를 만들 때 생성자를 위한 전달인자는 함수 호출처럼 전달됩니다. 모든 프로퍼티는 값이 할당될 필요가 있습니다 - 선언부(`numberOfSides`에서 그랬듯이) 또는 생성자(`name` 에서 그랬듯이) 중 한 곳에서 값이 반드시 할당되어야 합니다.

객체가 메모리에서 해제되기 전에 청소를 수행해야 한다면 디이니셜라이저(소멸자)를 만들기 위해 `deinit`을 사용하십시오.

하위 클래스는 자신의 클래스 이름 뒤에 콜론(`:`)으로 분리된 상위 클래스의 이름을 포함합니다. 클래스는 어떤 표준 루트 클래스도 상속하도록 요구하지 않습니다.* 따라서 필요한 대로 상위 클래스를 포함하거나 생략할 수 있습니다.

상위 클래스의 구현을 오버라이딩한 하위 클래스의 메서드는 `override`로 표시됩니다 - `override` 없이 실수로 오버라이딩한 메서드는 컴파일러 에러로 감지됩니다. 컴파일러는 상위 클래스에서 어떤 메서드도 오버라이딩하지 않는데 `override`가 붙어 있는 메서드 또한 감지합니다.

``` swift
class Square: NamedShape {
    var sideLength: Double

    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        numberOfSides = 4
    }

    func area() -> Double {
        return sideLength * sideLength
    }

    override func simpleDescription() -> String {
        return "A square with sides of length \(sideLength)."
    }
}
let test = Square(sideLength: 5.2, name: "my test square")
test.area()
test.simpleDescription()

```

> 실험
>
> `NamedShape`의 또 다른 하위 클래스인 `Circle`을 만들어 보십시오. 반지름을 가지고 생성자의 전달인자로서 이름을 가져야 합니다. `Circle`클래스의 메서드인 `area()` 와 `simpleDescription()`을 실행해 보십시오.

단순한 저장 프로퍼티에 더해서, 프로퍼티는 접근자(getter)와 설정자(setter)를 가질 수 있습니다.

``` swift
class EquilateralTriangle: NamedShape {
    var sideLength: Double = 0.0

    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        numberOfSides = 3
    }

    var perimeter: Double {
        get {
            return 3.0 * sideLength
        }
        set {
            sideLength = newValue / 3.0
        }
    }

    override func simpleDescription() -> String {
        return "An equilateral triangle with sides of length \(sideLength)."
    }
}
var triangle = EquilateralTriangle(sideLength: 3.1, name: "a triangle")
print(triangle.perimeter)
// Prints "9.3"
triangle.perimeter = 9.9
print(triangle.sideLength)
// Prints "3.3000000000000003"
```

`perimeter`의 설정자(setter)에서, 새로운 값은 `newValue`라는 암묵적 이름을 갖습니다. `set` 뒤의 소괄호 안에 명시적 이름을 지정할 수도 있습니다.

`EquilateralTriangle` 클래스의 생성자가 세 가지의 서로 다른 단계를 갖는 것에 주목하십시오 :

1. 하위 클래스가 선언한 프로퍼티의 값을 설정합니다. (`self.sideLength = sideLength`)
2. 상위 클래스의 생성자를 호출합니다. (`super.init(name:name)`)
3. 상위 클래스에 의해 정의된 프로퍼티의 값을 바꿉니다. 메서드/접근자(getter)/설정자(setter)를 사용하는 모든 추가적인 설정 작업 또한 이 시점에 이루어질 수 있습니다. (`numberOfSides = 3`)

만약 프로퍼티를 계산할 필요가 없지만 새로운 값을 설정하기 전이나 후에 실행되어야 할 코드가 있다면, `willSet` 과 `didSet` 을 사용하십시오. 당신이 설정한 코드는 생성자 밖에서 그 값이 변경될 때 마다 실행될 것입니다. 예를 들어, 아래의 클래스는 삼각형의 옆면의 길이가 언제나 사각형의 옆면의 길이와 같도록 보장합니다.

``` swift
class TriangleAndSquare {
    var triangle: EquilateralTriangle {
        willSet {
            square.sideLength = newValue.sideLength
        }
    }
    var square: Square {
        willSet {
            triangle.sideLength = newValue.sideLength
        }
    }
    init(size: Double, name: String) {
        square = Square(sideLength: size, name: name)
        triangle = EquilateralTriangle(sideLength: size, name: name)
    }
}
var triangleAndSquare = TriangleAndSquare(size: 10, name: "another test shape")
print(triangleAndSquare.square.sideLength)
// Prints "10.0"
print(triangleAndSquare.triangle.sideLength)
// Prints "10.0"
triangleAndSquare.square = Square(sideLength: 50, name: "larger square")
print(triangleAndSquare.triangle.sideLength)
// Prints "50.0"
```

옵셔널 값을 다룰 때는, 메서드/프로퍼티/서브스크립트와 같은 작업 앞에 `?` 을 사용할 수 있습니다. 만약 `?` 앞의 값이 nil이라면, `?` 뒤의 모든 것은 무시되고 그 표현식의 모든 값은 nil이 됩니다. 만약 그렇지 않으면, 옵셔널의 값이 벗겨지고 `?`뒤의 모든 것이 벗겨진 값으로서 실행됩니다. 두 경우 모두에서 전체 표현식의 값(`sideLength`)은 옵셔널 값입니다.

```swift
let optionalSquare: Square? = Square(sideLength: 2.5, name: "optional square")
let sideLength = optionalSquare?.sideLength
```

---

## 영단어 정리

- except -를 제외하고
- context 맥락. 문맥.
- likewise 비슷하게.
- distinguish A from B A를 B와 구별하다
- deinitializer 디이니셜라이저. 소멸자.
- deallocate 해제하다. (컴) 할당을 해제하다.
  - allocate 할당하다
- subclass 하위 클래스. 하위 분류 / (v) 하위 분류로 분류하다. (컴) 상속하다?
- superclass 상위 클래스. 상위 분류
- override ...보다 더 우선시하다. (컴) 오버라이드
- implementation 실행 (컴) 구현
  - implement 시행하다. (컴) 구현하다
- detect 감지하다. 알아내다.
- store (v) 저장하다
- declare 선언하다
- subscript (n) 아래에 적은 문자. (컴)서브스크립트
- subtitle 자막. 부제.
- subscribe 구독하다. 가입하다.
- set up 건립하다 / 준비하다.
- setup 설정
- cleanup 청소
- mark (v) 표시하다
- radius 반지름
- getter 접근자
- setter 설정자
- in addition (to ...) (...에) 더하여. 게다가.
- equilateral 등변의
- perimeter 둘레
- define 정의하다
- compute 계산하다
- perform 수행하다
- operation 작업
  - operator 연산자

