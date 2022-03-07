## Tuples

*Tuples* group multiple values into a single compound value.

튜플 그룹은 단일 합성 값에서 여러가지 값입니다.



 The values within a tuple can be of any type and don’t have to be of the same type as each other.

튜플 내부에 있는 값들은 어떤 타입이거나 서로 타입이 동일할 필요는 없습니다.



In this example, `(404, "Not Found")` is a tuple that describes an *HTTP status code*. 

예시에서, http 상태 코드를 묘사하는 튜플입니다.



An HTTP status code is a special value returned by a web server whenever you request a web page. 

당신이 웹페이지에 요청을하면 웹서버로부터 특별한 http 상태 코드를 받습니다.



A status code of `404 Not Found` is returned if you request a webpage that doesn’t exist.

404 낫 파운드 상태 코드는 웹페이지가 존재하지 않을때 전달받습니다.



The `(404, "Not Found")` tuple groups together an `Int` and a `String` to give the HTTP status code

two separate values: (a number and a human-readable description.)

해당 튜플은 인티저와 스트링으로 http 상태코드를 준다. 두가지 분리된 값들: 숫자 그리고 사람이 읽을 수 있는 설명



It can be described as “a tuple of type `(Int, String)`”.

튜플 타입은 위와같이 묘사된다.



You can create tuples from any permutation of types, and they can contain as many different types as you like. 

어떤 타입의 치환이든 만들 수 있다 그리고 여러가지 다른 종류의 타입을 포함할 수 있다.



There’s nothing stopping you from having a tuple of type `(Int, Int, Int)`, or `(String, Bool)`, or indeed any other permutation you require.

위의 예시 또는 심지어 당신이 원하는 치환의 타입 튜플을 갖도록 막는건 아무것도 없다.



You can *decompose* a tuple’s contents into separate constants or variables, which you then access as usual:

???, 튜플의 내용을 분리된 상수 또는 변수로 분해할 수 있습니다.



If you only need some of the tuple’s values, ignore parts of the tuple with an underscore (`_`) when you decompose the tuple:

만약 튜플 값들중 몇가지만 필요한다면, 튜플을 분해할 때 튜플의 무시할 부분을 _로 표시하세요.



Alternatively, access the individual element values in a tuple using index numbers starting at zero:

또는 0부터 시작하는 인덱스 넘버를 사용해서 튜플의 개개인의 값을 접근하세요.



You can name the individual elements in a tuple when the tuple is defined:

튜플이 정의될 때 각각 요소의 이름을 정할 수 있습니다.



If you name the elements in a tuple, you can use the element names to access the values of those elements:

튜플의 요소에다 이름을 명시했다면, 당신은 해당 요소들을 값을 요소 이름을 통해서 사용할 수 있습니다.



Tuples are particularly useful as the return values of functions. 

튜플은 값들을 리턴하는 함수에서 특히 유용합니다.



A function that tries to retrieve a web page might return the `(Int, String)` tuple type to describe the success or failure of the page retrieval. 

<어렵>웹페이지 검색을 시도하는 함수는 페이지 검색의 성공 또는 실패를 묘사하는 튜플 타입을 리턴할 것입니다. 



By returning a tuple with two distinct values, each of a different type, the function provides more useful information about its outcome than if it could only return a single value of a single type. 

<진짜 어렵>다른 타입을 각각, 두가지 별개의 값을 튜플로 리턴함으로써,  함수는  단일 타입의 단일 값을 리턴하는것보다 결과값에 사용할 수 있는 정보를 제공합니다. 



For more information, see [Functions with Multiple Return Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID164).

더 많은 정보는 여러가지 리턴값을 갖는 함수에서 확인할 수 있습니다.





Tuples are useful for simple groups of related values. 

튜플은 연관된 값들의 간단한 그룹들에게 유용합니다.



They’re not suited to the creation of complex data structures. 

튜플은 복잡한 데이터 구조의 생성에 적합하지 않습니다.



If your data structure is likely to be more complex, model it as a class or structure, rather than as a tuple. 

만약 당신의 데이터 구조가 더 복잡하다면 튜플을 사용하는 것보다 클래스나 구조체 모델하는게 좋을겁니다.



For more information, see [Structures and Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html).

더 자세한 내용은 구조체와 클래스에서 확인하세요.



compound: 합성의

permutation: 치환

decompose:  분해하다

Alternatively: 또는

particularly: 특히