# Enumerations and Structures

Use `enum` to create an enumeration.

열거형을 생성할 때 enum을 사용하세요



Like classes and all other named types, enumerations can have methods associated with them.

클래스와 다른 다른 티입들과 마찬가지로, 열거형은 그들의 연관된 메소드를 갖을 수 있습니다.



Write a function that compares two `Rank` values by comparing their raw values.

두가지 랭크값을 비교하는 메소드를 만드세요.



By default, Swift assigns the raw values starting at zero and incrementing by one each time, but you can change this behavior by explicitly specifying values.

기본적으로 스위프트는 할당합니다 날것의 값을 영부터 매번 하나씩 증가되도록, 그러나 값을 명시적으로 할당함으로써 변경할 수 있습니다.



 In the example above, `Ace` is explicitly given a raw value of `1`, and the rest of the raw values are assigned in order. 

예시에서 Ace에게 명시적으로 1값을 줬습니다. 그리고 나머지 값들은 순서대로 할당받았습니다.



You can also use strings or floating-point numbers as the raw type of an enumeration. 

너는 열거형의 타입을 문자열 플로팅포인트로 사용할 수 있습니다.



Use the `rawValue`property to access the raw value of an enumeration case.

열거형의 날거의 값을 접근할 때 rawValue를 사용하세요



Use the `init?(rawValue:)` initializer to make an instance of an enumeration from a raw value.

초기화를 통해서 열거형의 인스턴스를 만들 수 있습니다. 날것의 값으로 부터



It returns either the enumeration case matching the raw value or `nil` if there’s no matching `Rank`.

날것의 값과 매칭되는 랭크가 없다면 닐값을 뱉을겁니다.



The case values of an enumeration are actual values, not just another way of writing their raw values.  ???

열거형 케이스는 실질적인 값이 있습니다. 날것의 값을 작성하는 방법 뿐만아니라



In fact, in cases where there isn’t a meaningful raw value, you don’t have to provide one.

사실, 이경우 날것의 값이 의미있는건 아닙니다. 너는 제공할 필요가 업습니다.



Add a `color()` method to `Suit` that returns “black” for spades and clubs, and returns “red” for hearts and diamonds.

Suit에 color메소드를 추가하세요 특정 조건에 따라서 컬러 값을 리턴하세요.



Notice the two ways that the `hearts` case of the enumeration is referred to above: When assigning a value to the `hearts` constant, the enumeration case `Suit.hearts` is referred to by its full name because the constant doesn’t have an explicit type specified. 

투가지 방법에 주목해라, 하트 케이스는 아래로 추론된다. 하트 상수를 할당할 때 열거형 케이스 Suit.heart는 추론되어진다 풀네임으로 왜냐하면 그 상수는 명시적으로 타입이 아니기 때문에



Inside the switch, the enumeration case is referred to by the abbreviated form `.hearts` because the value of `self` is already known to be a suit.

스위치문 안에서 열거형 케이슨느 추론된다.  간결해진 형식으로 부터, .hearts 왜냐하면 셀프의 값은 이미 suit로 알려저있다.



You can use the abbreviated form anytime the value’s type is already known.

너는 값의 타입을 미리 알고 있다면 간결된 형식을 사용할 수 있다.



If an enumeration has raw values, those values are determined as part of the declaration, which means every instance of a particular enumeration case always has the same raw value. 

만약 열거형이 날것의 값들을 갖고 있다면, 그 값들은 선언될때 결정될것이다.  모든 인스턴스 특유의 열거형 케이스는 항상 같은 날것의 값을 갖여야한다는걸 의미한다.



Another choice for enumeration cases is to have values associated with the case—these values are determined when you make the instance, and they can be different for each instance of an enumeration case. 

열거형 케이스의 다른 선택은 케이스의 연관된 값을 갖는거다. 이 값들은 인스턴스를 생성할 떄 결정된다. 그리고 열거형 케이스의 인스턴스마다 다를 수 있다.



You can think of the associated values as behaving like stored properties of the enumeration case instance. 

너는 연관된 값이 열거형 케이스 인스턴스의 저장 프로퍼티처럼 생각할 수 있을것이다.



For example, consider the case of requesting the sunrise and sunset times from a server. 

예를 들어서 일출 그리고 일몰의 시간들이 서버로부터 요청되는 케이스를 고려해보자



The server either responds with the requested information, or it responds with a description of what went wrong.

그 서버는 둘다 응답한다.  요청된 정보, 또는 뭐가 잘못 온건지에 대한 설명



Add a third case to `ServerResponse` and to the switch.

리스폰스의 세번째 케이슬 추가하고 수위치문에 포함시켜라



Notice how the sunrise and sunset times are extracted from the `ServerResponse` value as part of matching the value against the switch cases. ???

주목해라 어떻게 일출과 일몰 시간이 서버응답 값으로으로부터 추출되는지 스위치 키에스에서 값을 매칭시키는걸



Use `struct` to create a structure. 

구조체를 만들 때 해당 키워드를 사용해라



Structures support many of the same behaviors as classes, including methods and initializers. 

구조체는 클래스와 동일한 행동을 지원한다. 메소드 그리고 초기화를 포함해서





One of the most important differences between structures and classes is that structures are always copied when they’re passed around in your code, but classes are passed by reference.

구조체와 클래스의 가장 큰 차이점은  구조체들은 항상 복사된다 너의 코드에서 전달될 떄, 그러나 레퍼런스를 전달한다.





Write a function that returns an array containing a full deck of cards, with one card of each combination of rank and suit.

함수를 작성하라 카드들의 덱 전부를 포함하는 배열을 리턴하도록, 하나의 카드에 랭크와 슈트가 조합되서



by one each time: 매번 하나씩

specified: 지정된, 명확히 서술된

abbreviated: 단축한, 간결된

particular: 특유의, 독특한

Sunrise: 일출

Sunset: 일몰

extracted: 뽑아내다, 추출하다