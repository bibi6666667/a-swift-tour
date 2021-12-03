## Type Annotations

You can provide a *type annotation* when you declare a constant or variable, to be clear about the kind of values the constant or variable can store.

상수나 변수를 선언할 때, 타입 주석을 제공할 수 있습니다. 상수 또는 변수가 저장할 수 있는 값의 종류에 대해서 명확하게 하기 위해서



Write a type annotation by placing a colon after the constant or variable name, followed by a space, followed by the name of the type to use.

상수 또는 변수 뒤에 콜론, 공백, 사용할 타입의 이름을 차례대로 배치해서 타입 주석을 작성해라.



This example provides a type annotation for a variable called `welcomeMessage`, to indicate that the variable can store `String` values:

그 변수는 스트링 값을 저장할 수 있는걸 나타내기 위해, 키워드로 불리는 값의 타입 주석을 제공합니다.



The colon in the declaration means “…of type…,” so the code above can be read as:

콜론 선언의 의미는 땡땡의 타입 그래서 위의 코드는 이와 같이 읽힌다



“Declare a variable called `welcomeMessage` that’s of type `String`.”

키워드로 불리는 값의 타입은 스트링으로 선언해라.



The phrase “of type `String`” means “can store any `String` value.” 

스트링 타입의 구문은 어떤 스트링 값도 저장할 수 있다를 의미한다.



Think of it as meaning “the type of thing” (or “the kind of thing”) that can be stored.

타입의 어떤것 (또는 어떤거의 종류) 저장될 수 있다라고 생각해라



The `welcomeMessage` variable can now be set to any string value without error:

에러를 제외하고 어떤 스트링 값도 저장할 수 있다.



You can define multiple related variables of the same type on a single line, separated by commas, with a single type annotation after the final variable name:

마지막 변수 이름 뒤 단일 타입 주석으로, 콤마로 분리된, 한줄에 같은 타입의 연관된 여러개의 값을 정의할 수 있다. 



It’s rare that you need to write type annotations in practice. 

 연습에서 타입 주석을 작성하는일은 거의 없을것이다.



If you provide an initial value for a constant or variable at the point that it’s defined, Swift can almost always infer the type to be used for that constant or variable, as described in [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322). 

정의되는 시점에 상수 또는 변수를 위한 초기 값을 제공한다면, 스위프트는 거의 항상 상수 또는 변수를 위해 사용될 타입 추론을 해줄것이다. 타입 안전 그리고 타입추론에서 묘사된것처럼



In the `welcomeMessage`example above, no initial value is provided, and so the type of the `welcomeMessage` variable is specified with a type annotation rather than being inferred from an initial value.

위의 예에서 키워드안에서 초기값이 제공되지 않았다 그래서 키워드 값은 명시되어졌다 타입 주석대신 초기 값으로 부터 추론되지도록





annotation: 주석

by placing Followed: 순서대로 배치하여 

above: 보다 위에