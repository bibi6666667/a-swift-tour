# A Swift Tour - Enumerations and Structures



> ## Enumerations and Structures
>
> Use `enum` to create an enumeration. Like classes and all other named types, enumerations can have methods associated with them.
>
> ``` swift
> enum Rank: Int {
>     case ace = 1
>     case two, three, four, five, six, seven, eight, nine, ten
>     case jack, queen, king
> 
>     func simpleDescription() -> String {
>         switch self {
>         case .ace:
>             return "ace"
>         case .jack:
>             return "jack"
>         case .queen:
>             return "queen"
>         case .king:
>             return "king"
>         default:
>             return String(self.rawValue)
>         }
>     }
> }
> let ace = Rank.ace
> let aceRawValue = ace.rawValue
> ```
>
> > EXPERIMENT
> >
> > Write a function that compares two `Rank` values by comparing their raw values.
>
> By default, Swift assigns the raw values starting at zero and incrementing by one each time, but you can change this behavior by explicitly specifying values. In the example above, `Ace` is explicitly given a raw value of `1`, and the rest of the raw values are assigned in order. You can also use strings or floating-point numbers as the raw type of an enumeration. Use the `rawValue` property to access the raw value of an enumeration case.
>
> Use the `init?(rawValue:)` initializer to make an instance of an enumeration from a raw value. It returns either the enumeration case matching the raw value or `nil` if there’s no matching `Rank`.
>
> ``` swift
> if let convertedRank = Rank(rawValue: 3) {
>     let threeDescription = convertedRank.simpleDescription()
> }
> ```
>
> The case values of an enumeration are actual values, not just another way of writing their raw values. In fact, in cases where there isn’t a meaningful raw value, you don’t have to provide one.
>
> ``` swift
> enum Suit {
>     case spades, hearts, diamonds, clubs
> 
>     func simpleDescription() -> String {
>         switch self {
>         case .spades:
>             return "spades"
>         case .hearts:
>             return "hearts"
>         case .diamonds:
>             return "diamonds"
>         case .clubs:
>             return "clubs"
>         }
>     }
> }
> let hearts = Suit.hearts
> let heartsDescription = hearts.simpleDescription()
> ```
>
> > EXPERIMENT
> >
> > Add a `color()` method to `Suit` that returns “black” for spades and clubs, and returns “red” for hearts and diamonds.
>
> Notice the two ways that the `hearts` case of the enumeration is referred to above: When assigning a value to the `hearts` constant, the enumeration case `Suit.hearts` is referred to by its full name because the constant doesn’t have an explicit type specified. Inside the switch, the enumeration case is referred to by the abbreviated form `.hearts` because the value of `self` is already known to be a suit. You can use the abbreviated form anytime the value’s type is already known.
>
> If an enumeration has raw values, those values are determined as part of the declaration, which means every instance of a particular enumeration case always has the same raw value. Another choice for enumeration cases is to have values associated with the case—these values are determined when you make the instance, and they can be different for each instance of an enumeration case. You can think of the associated values as behaving like stored properties of the enumeration case instance. For example, consider the case of requesting the sunrise and sunset times from a server. The server either responds with the requested information, or it responds with a description of what went wrong.
>
> ``` swift
> enum ServerResponse {
>     case result(String, String)
>     case failure(String)
> }
> 
> let success = ServerResponse.result("6:00 am", "8:09 pm")
> let failure = ServerResponse.failure("Out of cheese.")
> 
> switch success {
> case let .result(sunrise, sunset):
>     print("Sunrise is at \(sunrise) and sunset is at \(sunset).")
> case let .failure(message):
>     print("Failure...  \(message)")
> }
> // Prints "Sunrise is at 6:00 am and sunset is at 8:09 pm."
> ```
>
> > EXPERIMENT
> >
> > Add a third case to `ServerResponse` and to the switch.
>
> Notice how the sunrise and sunset times are extracted from the `ServerResponse` value as part of matching the value against the switch cases.
>
> Use `struct` to create a structure. Structures support many of the same behaviors as classes, including methods and initializers. One of the most important differences between structures and classes is that structures are always copied when they’re passed around in your code, but classes are passed by reference.
>
> ``` swift
> struct Card {
>     var rank: Rank
>     var suit: Suit
>     func simpleDescription() -> String {
>         return "The \(rank.simpleDescription()) of \(suit.simpleDescription())"
>     }
> }
> let threeOfSpades = Card(rank: .three, suit: .spades)
> let threeOfSpadesDescription = threeOfSpades.simpleDescription()
> ```
>
> >  EXPERIMENT
> >
> > Write a function that returns an array containing a full deck of cards, with one card of each combination of rank and suit.



## 열거형과 구조체

열거형을 만들기 위해 `enum`을 사용하십시오. 클래스와 다른 지정된 타입들처럼, 열거형도 연관된 메서드를 가질 수 있습니다.

``` swift
enum Rank: Int {
    case ace = 1
    case two, three, four, five, six, seven, eight, nine, ten
    case jack, queen, king

    func simpleDescription() -> String {
        switch self {
        case .ace:
            return "ace"
        case .jack:
            return "jack"
        case .queen:
            return "queen"
        case .king:
            return "king"
        default:
            return String(self.rawValue)
        }
    }
}
let ace = Rank.ace
let aceRawValue = ace.rawValue
```

> 실험
>
> 원시값을 비교함으로써 두 `Rank` 값을  비교하는 메서드를 작성해 보십시오.

기본적으로, 스위프트는 원시값을 0부터 하나씩 증가하는 값으로 할당합니다. 하지만 특정 값을 명시적으로 지정함으로써 이 동작을 바꿀 수 있습니다. 위의 예시에서, `Ace`는 명시적으로 1의 원시값을 가지며, 나머지의 원시값은 순서대로 할당되었습니다. 또한 열거형의 원시값으로 문자열이나 부동소수점 숫자를 사용할 수도 있습니다. 열거형 케이스의 원시값에 접근하기 위해 `rawValue` 프로퍼티를 사용하십시오.

원시값으로부터 열거형의 인스턴스를 만들기 위해 `init?(rawValue:)` 생성자를 사용하십시오. 원시값에 맞는 케이스가 있다면 그 열거형을 반환하거나, 맞는 케이스가 없다면 nil을 반환합니다.

``` swift
if let convertedRank = Rank(rawValue: 3) {
    let threeDescription = convertedRank.simpleDescription() // three
}
```

열거형의 케이스 값은 실제 값이며, 원시값을 다른 방식으로 작성한 것이 아닙니다. 사실, 의미 있는 원시값이 없는 케이스에는 원시값을 반드시 지정하지 않아도 됩니다.

``` swift
enum Suit {
    case spades, hearts, diamonds, clubs

    func simpleDescription() -> String {
        switch self {
        case .spades:
            return "spades"
        case .hearts:
            return "hearts"
        case .diamonds:
            return "diamonds"
        case .clubs:
            return "clubs"
        }
    }
}
let hearts = Suit.hearts
let heartsDescription = hearts.simpleDescription()
```

> 실험
>
> spades와 clubs에 대해 "black"을, hearts와 diamonds에 대해 "red"를 반환하는 `Suit`의 메서드 `color()` 를 추가하십시오.

위처럼 열거형의 `hearts` 케이스가 두 방식으로 추론됨을 주목하십시오. `hearts` 상수에 값을 할당할 때, 열거형 케이스 `Suit.hearts`는 그것의 전체 이름으로 추론됩니다. 왜냐하면 상수가 지정된 명시적 타입이 없기 때문입니다. switch문에서는, 열거형의 케이스는 `.hearts`라는 축약된 형태로 추론됩니다. 왜냐하면 `self`의 값이 이미 `Suit`라고 알려져 있기 때문입니다. 값의 타입이 이미 알려져 있다면 언제나 축약된 형태를 사용할 수 있습니다.

만약 열거형이 원시값을 가지고 있다면, 그 값들은 선언의 일부로 결정됩니다. 이는 특정 열거형 케이스의 모든 인스턴스가 항상 같은 원시값을 가짐을 의미합니다. 열거형 케이스에 대한 또 다른 선택은 케이스와 연관된 값(연관값)을 가지게 하는 것입니다 - 이 값들은 인스턴스를 만들 때 결정되며, 열거형 케이스의 인스턴스마다 다른 값을 가질 수 있습니다. 연관값은 열거형 케이스 인스턴스의 저장 프로퍼티와 같이 동작한다고 생각할 수 있습니다. 예를 들어, 서버로부터 일출과 일몰 시간을 요청하는 경우를 고려해 보십시오. 서버는 요청받은 정보를 응답하거나, 잘못되었을 때의 설명을 응답할 수 있습니다.

``` swift
enum ServerResponse {
    case result(String, String)
    case failure(String)
}

let success = ServerResponse.result("6:00 am", "8:09 pm")
let failure = ServerResponse.failure("Out of cheese.")

switch success {
case let .result(sunrise, sunset): // 열거형의 연관값을 사용하기 위해 case let 사용하고 그 이름을 부여함
    print("Sunrise is at \(sunrise) and sunset is at \(sunset).")
case let .failure(message):
    print("Failure...  \(message)")
}
// Prints "Sunrise is at 6:00 am and sunset is at 8:09 pm."
```

> 실험
>
> `ServerResponse`와 switch 문에 세 번째 케이스를 추가해 보십시오.

switch 케이스에 대해 맞는 값의 일부로서 일출과 일몰 시간이  `ServerResponse` 값으로부터 어떻게 추출되었는지 주목하십시오.

구조체를 만들기 위해  `struct`를 사용하십시오. 구조체는 메서드와 생성자를 포함해 클래스처럼 많은 같은 동작을 지원합니다. 구조체와 클래스의 가장 중요한 차이점 중 하나는, 구조체는 코드에서 전달될 때 항상 복사되지만, 클래스는 참조로 전달된다는 것입니다.

``` swift
struct Card {
    var rank: Rank
    var suit: Suit
    func simpleDescription() -> String {
        return "The \(rank.simpleDescription()) of \(suit.simpleDescription())"
    }
}
let threeOfSpades = Card(rank: .three, suit: .spades)
let threeOfSpadesDescription = threeOfSpades.simpleDescription(
```

> 실험
>
> 카드 한 장 마다 Rank와 Suit의 조합을 갖는 모든 카드 덱의 배열을 반환하는 함수를 작성해 보십시오.





## 단어 정리

- enumeration 열거. (컴) 열거형
  - enumerate 열거하다
- named 지명된 / 유명한
- specify 지정하다
- increment 증가
- abbreviate 줄이다. 축약하다.
- raw value 원시값
- associated value 연관값
- extract 추출(하다)
- determine (...를) 결정하다
- deck  덱. 한벌.
- combination 조합
- infer 추론하다
- refer 참조하다

> Notice the two ways that the `hearts` case of the enumeration is referred to above

>  Inside the switch, the enumeration case is referred to by the abbreviated form `.hearts` because the value of `self` is already known to be a suit.

> You can use the abbreviated form anytime the value’s type is already known.