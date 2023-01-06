# The Basics - Constants and Variables (3),  Comments

## Printing Constants and Variables
You can print the current value of a constant or variable with the `print(_:separator:terminator:)` function:
``` swift
print(friendlyWelcome)
// Prints "Bonjour!"
```
The `print(_:separator:terminator:)` function is a global function that prints one or more values to an appropriate output. In Xcode, for example, the `print(_:separator:terminator:)` function prints its output in Xcode’s “console” pane. The separator and terminator parameter have default values, so you can omit them when you call this function. By default, the function terminates the line it prints by adding a line break. To print a value without a line break after it, pass an empty string as the terminator—for example, `print(someValue, terminator: "")`. For information about parameters with default values, see  [Default Parameter Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID169) .
Swift uses string interpolation to include the name of a constant or variable as a placeholder in a longer string, and to prompt Swift to replace it with the current value of that constant or variable. Wrap the name in parentheses and escape it with a backslash before the opening parenthesis:
``` swift
print("The current value of friendlyWelcome is \(friendlyWelcome)")
// Prints "The current value of friendlyWelcome is Bonjour!"
```
> NOTE  
> All options you can use with string interpolation are described in  [String Interpolation](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html#ID292) .  

# Comments
Use comments to include nonexecutable text in your code, as a note or reminder to yourself. Comments are ignored by the Swift compiler when your code is compiled.
Comments in Swift are very similar to comments in C. Single-line comments begin with two forward-slashes (//):
``` swift 
// This is a comment.
```
Multiline comments start with a forward-slash followed by an asterisk (/*) and end with an asterisk followed by a forward-slash (*/):
``` swift
 /* This is also a comment
but is written over multiple lines. */
```
Unlike multiline comments in C, multiline comments in Swift can be nested inside other multiline comments. You write nested comments by starting a multiline comment block and then starting a second multiline comment within the first block. The second block is then closed, followed by the first block:
``` swift
/* This is the start of the first multiline comment.
 /* This is the second, nested multiline comment. */
This is the end of the first multiline comment. */ 
```
Nested multiline comments enable you to comment out large blocks of code quickly and easily, even if the code already contains multiline comments.

- - - -

### Printing Constants and Variables
변수와 상수 출력하기
`print(_:separator:terminator:)` 함수로 현재의 상수 또는 변수의 값을 출력할 수 있습니다 :
``` swift
print(friendlyWelcome)
// Prints "Bonjour!"
```
`print(_:separator:terminator:)` 함수는 하나 또는 여러 값들을 적절한 산출물로 출력하는 전역 함수입니다. Xcode에서는, 예를 들면, `print(_:separator:terminator:)` 함수는 산출물을 Xcode의 "콘솔" 창에 출력합니다. `separator`와 `terminator` 매개변수는 기본값을 가지고 있으므로, 이 함수를 호출할 때 생략할 수 있습니다. 기본적으로, 이 함수는 출력하는 줄 끝에 줄바꿈 문자를 더해 끝냅니다. 값의 끝에 줄바꿈 문자를 빼고 출력하기 위해서는, `terminator`로 빈 문자열을 전달하십시오 - 예를 들어, `print(someValue, terminator: "")`. 기본값을 가진 매개변수에 대한 더 많은 정보를 위해서는, [Default Parameter Values](https://docs.swift.org/swift-book/LanguageGuide/Functions.html#ID169) 를 참고하십시오.

스위프트는 변수 또는 상수의 이름을 더 긴 문자열에 플레이스홀더로 포함시키기 위해, 그리고 스위프트가 그것을 상수 또는 변수의 현재 값으로 대체하도록 하기 위해 *문자열 보간법*을 사용합니다. 이름을 소괄호로 감싸고, 여는 소괄호 앞에 백슬래시를 붙여 빠져나오십시오 : 
``` swift
print("The current value of friendlyWelcome is \(friendlyWelcome)")
// Prints "The current value of friendlyWelcome is Bonjour!"
```

> 노트  
> 문자열 보간법에 사용할 수 있는 모든 옵션들은  [String Interpolation](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html#ID292) 에 설명되어 있습니다.  

## Comments
주석
코드에 실행할 수 없는 텍스트를 포함시키기 위해 주석을 사용하십시오. 메모 또는 리마인더로 사용할 수 있습니다. 주석은 코드가 컴파일 될 때 스위프트 컴파일러에 의해 무시됩니다.
스위프트에서의 주석은 C언어의 주석과 매우 비슷합니다. 한 줄 주석은 두 개의 슬래시(`//`)로 시작합니다 :
``` swift
// This is a comment.
```
여러 줄 주석은 슬래시와 별표(`/*`)로 시작하고 별표와 슬래시(`*/`)로 끝납니다 :
``` swift
/* This is also a comment
but is written over multiple lines. */
```

C언어의 여러 줄 주석과 다르게, 스위프트의 여러 줄 주석은 다른 여러 줄 주석과 중첩될 수 있습니다. 중첩 주석은 여러 줄 주석을 열고, 두 번째 여러 줄 주석을 첫 번째 블럭 안에서 열어 작성합니다. 그 뒤 두 번째 블럭이 닫히고, 첫 번째 블럭이 계속됩니다.
``` swift
/* This is the start of the first multiline comment.
 /* This is the second, nested multiline comment. */
This is the end of the first multiline comment. */
```
여러 줄 중첩 주석은 큰 코드 블럭이 이미 여러 줄 주석으로 포함하고 있더라도, 빠르고 쉽게 주석 처리하는 것을 가능하게 해 줍니다.
- - - -

## 단어 정리
- pane 판유리. 창. (컴) 창.
- separator 구분자
- terminator 종결자
- global function 전역 함수
- output 산출
- line break 줄바꿈 문자
- empty string 빈 문자열
- interpolation 써넣음/써넣은 어구. 보간법.
	- string interpolation 문자열 보간법
- prompt (동) 촉발하다. ~하도록 하다. (형) 즉각적인
- placeholder 플레이스 홀더
- nonexecutable 비실행의. 실행할 수 없는.
- reminder 상기시키는 것(편지/메모)
- forward-slash (`/`)
- backslash (`\`)
- asterisk (`*`) 별표
- within ~안에. ~이내에. (기간/거리)
- multiline 여러 줄의 
- comment out (컴) 주석 처리하다.
	- uncomment (컴) 주석을 제거하다.
