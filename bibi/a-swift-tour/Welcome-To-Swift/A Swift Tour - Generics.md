# A Swift Tour - Generics

> Write a name inside angle brackets to make a generic function or type.
>
> ``` swift
> func makeArray<Item>(repeating item: Item, numberOfTimes: Int) -> [Item] {
>     var result: [Item] = []
>     for _ in 0..<numberOfTimes {
>         result.append(item)
>     }
>     return result
> }
> makeArray(repeating: "knock", numberOfTimes: 4)
> ```
>
> You can make generic forms of functions and methods, as well as classes, enumerations, and structures.
>
> ``` swift
> // Reimplement the Swift standard library's optional type
> enum OptionalValue<Wrapped> {
>     case none
>     case some(Wrapped)
> }
> var possibleInteger: OptionalValue<Int> = .none
> possibleInteger = .some(100)
> ```
>
> Use `where` right before the body to specify a list of requirements—for example, to require the type to implement a protocol, to require two types to be the same, or to require a class to have a particular superclass.
>
> ``` swift
> func anyCommonElements<T: Sequence, U: Sequence>(_ lhs: T, _ rhs: U) -> Bool
>     where T.Element: Equatable, T.Element == U.Element
> {
>     for lhsItem in lhs {
>         for rhsItem in rhs {
>             if lhsItem == rhsItem {
>                 return true
>             }
>         }
>     }
>     return false
> }
> anyCommonElements([1, 2, 3], [3])
> ```
>
> > EXPERIMENT
> >
> > Modify the `anyCommonElements(_:_:)` function to make a function that returns an array of the elements that any two sequences have in common.
>
> Writing `<T: Equatable>` is the same as writing `<T> ... where T: Equatable`.



### 제네릭

제네릭 함수나 타입을 만들기 위해 꺾쇠 괄호 안에 이름을 작성하십시오.

``` swift
func makeArray<Item>(repeating item: Item, numberOfTimes: Int) -> [Item] {
    var result: [Item] = []
    for _ in 0..<numberOfTimes {
        result.append(item)
    }
    return result
}
makeArray(repeating: "knock", numberOfTimes: 4)
```

함수와 메서드, 클래스, 열거형, 구조체의 제네릭 형태를 만들 수 있습니다.

``` swift
// Reimplement the Swift standard library's optional type
enum OptionalValue<Wrapped> {
    case none
    case some(Wrapped)
}
var possibleInteger: OptionalValue<Int> = .none
possibleInteger = .some(100)
```

코드 몸통(body) 바로 앞에 where를 사용해 요건 목록을 지정하십시오 - 예를 들어, 프로토콜을 구현하기 위한 타입을 요구하거나, 두 타입이 같기를 요구하거나, 클래스가 특정 상위 클래스를 갖도록 요구하기 위해 사용할 수 잆습니다.

``` swift
func anyCommonElements<T: Sequence, U: Sequence>(_ lhs: T, _ rhs: U) -> Bool
    where T.Element: Equatable, T.Element == U.Element
{
    for lhsItem in lhs {
        for rhsItem in rhs {
            if lhsItem == rhsItem {
                return true
            }
        }
    }
    return false
}
anyCommonElements([1, 2, 3], [3])
```

> 실험
>
> `anyCommonElements(_:_:)`함수가 어떤 두 시퀀스를 공통으로 갖는 요소의 배열을 반환하는 함수를 만들도록 수정하십시오.

`<T: Equatable>`을 작성하는 것은 `<T> ... where T: Equatable`을 작성하는 것과 같습니다.



## 단어 정리

- angle bracket 꺾쇠 괄호 (`<>`)

- requirement 필요 조건

- equatable 동일시할 수 있는
  - equate 동일시하다
  
- sequence 순서. 연속적인 것. (v) 차례로 배열하다.

  - (컴) 순서가 있는 타입? 배열, 리스트 등.. (타입) 시퀀스(Sequence)

- as well as ...에 더하여.

- reimplement 재구현

- modify A to B A를 B로 수정하다?

  