# The Basics - Tuples



*Tuples* group multiple values into a single compound value. The values within a tuple can be of any type and don’t have to be of the same type as each other.

In this example, `(404, "Not Found")` is a tuple that describes an *HTTP status code*. An HTTP status code is a special value returned by a web server whenever you request a web page. A status code of `404 Not Found` is returned if you request a webpage that doesn’t exist.

``` swift
let http404Error = (404, "Not Found")
// http404Error is of type (Int, String), and equals (404, "Not Found")
```

The `(404, "Not Found")` tuple groups together an `Int` and a `String` to give the HTTP status code two separate values: a number and a human-readable description. It can be described as “a tuple of type `(Int, String)`”.

You can create tuples from any permutation of types, and they can contain as many different types as you like. There’s nothing stopping you from having a tuple of type `(Int, Int, Int)`, or `(String, Bool)`, or indeed any other permutation you require.

You can *decompose* a tuple’s contents into separate constants or variables, which you then access as usual:

``` swift
let (statusCode, statusMessage) = http404Error
print("The status code is \(statusCode)")
// Prints "The status code is 404"
print("The status message is \(statusMessage)")
// Prints "The status message is Not Found"
```

If you only need some of the tuple’s values, ignore parts of the tuple with an underscore (`_`) when you decompose the tuple:

``` swift
let (justTheStatusCode, _) = http404Error
print("The status code is \(justTheStatusCode)")
// Prints "The status code is 404"
```

Alternatively, access the individual element values in a tuple using index numbers starting at zero:

``` swift
print("The status code is \(http404Error.0)")
// Prints "The status code is 404"
print("The status message is \(http404Error.1)")
// Prints "The status message is Not Found"
```

You can name the individual elements in a tuple when the tuple is defined:

``` swift
let http200Status = (statusCode: 200, description: "OK")
```

If you name the elements in a tuple, you can use the element names to access the values of those elements:

``` swift
print("The status code is \(http200Status.statusCode)")
// Prints "The status code is 200"
print("The status message is \(http200Status.description)")
// Prints "The status message is OK"
```

Tuples are particularly useful as the return values of functions. A function that tries to retrieve a web page might return the `(Int, String)` tuple type to describe the success or failure of the page retrieval. By returning a tuple with two distinct values, each of a different type, the function provides more useful information about its outcome than if it could only return a single value of a single type. For more information, see [Functions with Multiple Return Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID164).

>  NOTE
>
> Tuples are useful for simple groups of related values. They’re not suited to the creation of complex data structures. If your data structure is likely to be more complex, model it as a class or structure, rather than as a tuple. For more information, see [Structures and Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html).



---

## Tuples

튜플

*튜플*은 여러 개의 값들을 하나의 복합적인 값으로 묶습니다. 튜플 안의 값들은 어떤 타입이든 가능하며 서로 같은 타입일 필요도 없습니다.

이 예시에서, `(404, "Not Found")` 는 HTTP 상태 코드를 나타내는 튜플입니다. HTTP 상태 코드는 당신이 웹 페이지를 요청했을 때 언제든지 웹 서버로부터 반환되는 특별한 값입니다. `404 Not Found`는 당신이 존재하지 않는 웹 페이지를 요청했을 때 반환됩니다.

``` swift
let http404Error = (404, "Not Found")
// http404Error는 (Int, String) 타입이며, (404, "Not Found")와 같습니다.
```

`(404, "Not Found")`튜플은 HTTP 상태 코드의 두 개의 개별적인 값을 주기 위해, 숫자와 인간이 읽기 쉬운 설명인 Int 와 String 을 함께 묶습니다. 이것은 "(Int, String) 타입의 튜플"이라고 설명할 수 있습니다.

당신은 어떤 타입의 순열로도 튜플을 만들 수 있고, 원하는 만큼 많은 다른 타입을 담을 수도 있습니다. (Int, Int, Int), (String, Bool) 타입 또는 당신이 필요한 어떤 순열의 튜플을 만드는 것으로부터 당신을 막는 것은 정말 아무것도 없습니다.

튜플의 내용을 개별적인 상수나 변수로 분해할 수 있으며, 보통 그 다음 그 값에 접근합니다 :

``` swift
let (statusCode, statusMessage) = http404Error
print("The status code is \(statusCode)")
// "The status code is 404" 를 출력합니다.
print("The status message is \(statusMessage)")
// "The status message is Not Found"를 출력합니다.
```

만약 튜플의 값 일부만이 필요하다면, 튜플을 분해할 때 언더바(`_`)로 튜플의 일부를 무시할 수 있습니다 : 

``` swift
let (justTheStatusCode, _) = http404Error
print("The status code is \(justTheStatusCode)")
// "The status code is 404" 를 출력합니다.
```

대안적으로, 0부터 시작하는 인덱스 번호를 사용해 튜플 안의 개별 요소 값에 접근하십시오 :

``` swift
print("The status code is \(http404Error.0)")
// "The status code is 404" 를 출력합니다.
print("The status message is \(http404Error.1)")
// "The status message is Not Found" 를 출력합니다.            
```

튜플이 정의될 때, 튜플 안의 개별 요소들에 이름을 지어줄 수 있습니다 : 

``` swift
let http200Status = (statusCode: 200, description: "OK")
```

만약 튜플 안의 요소들에 이름을 지어준다면, 그 요소들의 값에 접근하기 위해 요소 이름을 사용할 수 있습니다 :

``` swift
print("The status code is \(http200Status.statusCode)")
// "The status code is 200" 을 출력합니다.
print("The status message is \(http200Status.description)")
// "The status message is OK" 를 출력합니다.
```

튜플은 특히 함수의 리턴 값으로서 유용합니다. 웹 페이지를 검색하려는 함수는 페이지 검색의 성공 또는 실패를 설명하기 위해 (Int, String) 튜플 타입을 리턴할 것입니다. 각각 다른 타입의 별개의 두 값을 튜플로 반환함으로써, 함수는 하나의 타입의 하나의 값만 리턴할 수 있었을 때 보다, 결과에 대한 더 유용한 정보를 제공합니다. 더 많은 정보를 위해서는, [Functions with Multiple Return Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID164)를 보십시오.

> 노트
>
> 튜플은 연관된 값들의 간단한 그룹에 유용합니다. 튜플은 복잡한 데이터 구조의 생성에는 어울리지 않습니다. 만약 당신의 데이터 구조가 더 복잡해질 것 같다면, 튜플보다는 클래스 또는 구조체로 만드십시오. 더 많은 정보를 위해서는, [Structures and Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html)를 보십시오.

---



## 단어 정리

- whenever 언제든지
- permutation 순열. 순차적인 조합
- indeed (부사) 정말. 참으로.
- decompose 분해하다
- retrieve 검색하다
- describe 설명하다
- distinct 별개의
- suit 어울리게 하다. ...에게 어울리다.
- model (v) 만들다