# The Basics - Constants and Variables (2)

## Type Annotations
You can provide a type annotation when you declare a constant or variable, to be clear about the kind of values the constant or variable can store. Write a type annotation by placing a colon after the constant or variable name, followed by a space, followed by the name of the type to use.
This example provides a type annotation for a variable called `welcomeMessage`, to indicate that the variable can store `String` values:
``` swift
var welcomeMessage: String
```
The colon in the declaration means “…of type…,” so the code above can be read as:
“Declare a variable called `welcomeMessage` that’s of type `String`.”
The phrase “of type `String`” means “can store any `String` value.” Think of it as meaning “the type of thing” (or “the kind of thing”) that can be stored.
The `welcomeMessage` variable can now be set to any string value without error:
``` swift
welcomeMessage = "Hello"
```
You can define multiple related variables of the same type on a single line, separated by commas, with a single type annotation after the final variable name:
``` swift
var red, green, blue: Double
```
> NOTE  
> It’s rare that you need to write type annotations in practice. If you provide an initial value for a constant or variable at the point that it’s defined, Swift can almost always infer the type to be used for that constant or variable, as described in  [Type Safety and Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322) . In the welcomeMessage example above, no initial value is provided, and so the type of the welcomeMessage variable is specified with a type annotation rather than being inferred from an initial value.  

## Naming Constants and Variables
Constant and variable names can contain almost any character, including Unicode characters:
``` swift
let π = 3.14159
let 你好 = "你好世界"
let 🐶🐮 = "dogcow"
```
Constant and variable names can’t contain whitespace characters, mathematical symbols, arrows, private-use Unicode scalar values, or line- and box-drawing characters. Nor can they begin with a number, although numbers may be included elsewhere within the name.
Once you’ve declared a constant or variable of a certain type, you can’t declare it again with the same name, or change it to store values of a different type. Nor can you change a constant into a variable or a variable into a constant.
> NOTE  
> If you need to give a constant or variable the same name as a reserved Swift keyword, surround the keyword with backticks (`) when using it as a name. However, avoid using keywords as names unless you have absolutely no choice.  
You can change the value of an existing variable to another value of a compatible type. In this example, the value of friendlyWelcome is changed from "`Hello`!" to "`Bonjour`!":
``` swift
var friendlyWelcome = "Hello!"
friendlyWelcome = "Bonjour!"
// friendlyWelcome is now "Bonjour!"
```
Unlike a variable, the value of a constant can’t be changed after it’s set. Attempting to do so is reported as an error when your code is compiled:
``` swift
let languageName = "Swift"
languageName = "Swift++"
// This is a compile-time error: languageName cannot be changed.
```

- - - -

### 타입 어노테이션

상수 또는 변수가 저장할 수 있는 값의 유형을 명확히 하기 위해, 상수 또는 변수를 선언할 때 타입 어노테이션을 사용할 수 있습니다. 상수 또는 변수의 이름 뒤에 콜론(`:`)과 띄어쓰기, 사용할 타입의 이름을 작성함으로써 타입 어노테이션을 사용하십시오.
이 예시는 이 변수가 `String`값을 저장할 수 있음을 나타내기 위해,  `welcomeMessage`라는 이름의 변수에 대해 타입 어노테이션을 제공합니다.
``` swift
var welcomeMessage: String
```
선언의 콜론은 "...는 ...타입이다"를 의미하며, 따라서 위의 코드는 다음과 같이 읽을 수 있습니다 : 
" `String`타입인 `welcomeMessage`라는 이름의변수를 선언한다"
"타입이 String인"이라는 구절은 "어떤 String값도 담을 수 있는"을 의미합니다. 저장될 수 있는 대상의 타입 (또는 대상의 종류)를 의미한다고 생각하십시오.
`welcomeMessage` 변수는 에러 없이 어떤 문자열 값으로도 지정될 수 있습니다.
``` swift
welcomeMessage = "Hello"
```
동일한 타입의 여러 개의 관련된 변수를 한 줄로 정의할 수 있으며, 콤마(`,`)로 구분하고 마지막 변수명 뒤에 타입 어노테이션을 붙이면 됩니다.
``` swift
var red, green, blue: Double
```
> 노트  
> 실제로 타입 어노테이션을 작성해야 할 필요는 거의 없습니다. [타입 안전성과 타입 추론]([The Basics — The Swift Programming Language (Swift 5.5)](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322))에 설명된 것처럼, 만약 상수 또는 변수가 정의되는 시점에 초기값을 제공한다면 스위프트는 거의 항상 그 상수 또는 변수에서 사용될 타입을 추론합니다.  위의 `welcomeMessage` 예시에서, 초기값이 제공되지 않았고, 따라서`welcomeMessage` 변수의 타입은 초기값으로부터 추론되기보다는 타입 어노테이션으로 구체화됩니다.  

### 상수 및 변수명 짓기
상수와 변수의 이름은 유니코드 문자를 포함해 거의 모든 문자를 포함할 수 있습니다 : 
``` swift
let π = 3.14159
let 你好 = "你好世界"
let 🐶🐮 = "dogcow"
```

상수와 변수 이름은 공백문자, 수학 기호, 화살표, 전용 유니코드 스칼라 값, 선 그리기 또는 상자 그리기 문자를 포함할 수 없습니다. 또한 이름 안에 숫자를 포함할 수 있지만 숫자로 시작할 수는 없습니다.
한 번 상수나 변수를 특정 타입으로 선언하면, 같은 이름으로 다시 선언하거나 다른 타입의 값을 담도록 바꿀 수 없습니다. 또한 상수를 변수로 바꾸거나 변수를 상수로 바꿀 수도 없습니다.
> 노트  
> 만약 상수나 변수에 스위프트 키워드와 같은 이름을 사용해야 한다면, 그것을 이름으로 사용할 때 키워드를 백틱(`)으로 감싸십시오. 하지만, 다른 방법이 전혀 없지 않은 한 키워드를 이름으로 사용하는 것을 피하십시오.  
존재하는 변수의 값을 호환되는 타입의 다른 값으로 바꿀 수 있습니다. 이 예시에서, `friendlyWlecome`의 값은 `"Hello!"`에서 `"Bonjour!"`로 바뀌었습니다.
``` swift
var friendlyWelcome = "Hello!"
friendlyWelcome = "Bonjour!"
// friendlyWelcome is now "Bonjour!"
```
변수와 다르게, 상수의 값은 설정되고 난 뒤에는 바뀔 수 없습니다. 그렇게 바꾸기 위한 시도는 코드가 컴파일될 때 에러로 보고됩니다 :
``` swift
let languageName = "Swift"
languageName = "Swift++"
// This is a compile-time error: languageName cannot be changed.
```


- - - -
## 단어 정리
- annotation 주석(을 달기)
- in practice 실제는. 사실상.
- nor (접속사/부사) ...도 아니다/없다.
- compatible 호환이 되는
- phrase 구절
- think of it as ... ...라고 생각하다.
- private use 사적 이용. 전용.

