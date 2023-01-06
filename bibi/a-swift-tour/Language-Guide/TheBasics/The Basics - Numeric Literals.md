# The Basics - Numeric Literals
Integer literals can be written as:
* A decimal number, with no prefix
* A binary number, with a 0b prefix
* An octal number, with a 0o prefix
* A hexadecimal number, with a 0x prefix
All of these integer literals have a decimal value of 17:
``` swift
let decimalInteger = 17
let binaryInteger = 0b10001       // 17 in binary notation
let octalInteger = 0o21           // 17 in octal notation
let hexadecimalInteger = 0x11     // 17 in hexadecimal notation
```
Floating-point literals can be decimal (with no prefix), or hexadecimal (with a 0x prefix). They must always have a number (or hexadecimal number) on both sides of the decimal point. Decimal floats can also have an optional exponent, indicated by an uppercase or lowercase e; hexadecimal floats must have an exponent, indicated by an uppercase or lowercase p.
For decimal numbers with an exponent of exp, the base number is multiplied by 10exp:
* 1.25e2 means 1.25 x 102, or 125.0.
* 1.25e-2 means 1.25 x 10-2, or 0.0125.
For hexadecimal numbers with an exponent of exp, the base number is multiplied by 2exp:
* 0xFp2 means 15 x 22, or 60.0.
* 0xFp-2 means 15 x 2-2, or 3.75.
All of these floating-point literals have a decimal value of 12.1875:
``` swift
let decimalDouble = 12.1875
let exponentDouble = 1.21875e1
let hexadecimalDouble = 0xC.3p0
```
Numeric literals can contain extra formatting to make them easier to read. Both integers and floats can be padded with extra zeros and can contain underscores to help with readability. Neither type of formatting affects the underlying value of the literal:
``` swift
let paddedDouble = 000123.456
let oneMillion = 1_000_000
let justOverOneMillion = 1_000_000.000_000_1
```


- - - -
### Numeric Literals
숫자  리터럴

정수 리터럴은 다음과 같이 작성될 수 있습니다:
- 접두사 없는 10진법 숫자
- `0b` 접두사를 갖는 2진법 숫자
- `0o` 접두사를 갖는 8진법 숫자
- `0x` 접두사를 갖는 16진법 숫자
아래의 모든 정수 리터럴은 모두 10진법으로 17의 값을 갖습니다:
``` swift
let decimalInteger = 17
let binaryInteger = 0b10001       // 2진법으로 17
let octalInteger = 0o21           // 8진법으로 17
let hexadecimalInteger = 0x11     // 16진법으로 17
```

부동소수점 리터럴은 10진법이나(접두사 없이) 16진법(`0x` 접두사와 함께)이 될 수 있습니다. 그것은 반드시 항상 소수점 양 옆에 숫자(또는 16진법 숫자)가 있어야 합니다. 10진법 실수는 또한 선택적으로 지수를 가질 수 있으며, 대문자 또는 소문자 `e`로 나타냅니다; 16진법 실수는 반드시 지수를 가져야 하며, 대문자 또는 소문자 `p`로 나타냅니다.
`exp`의 지수를 갖는 10진법 숫자의 경우, 밑에 `10의 exp승`를 곱합니다:
* `1.25e2` 는 `1.25 x 10의 2승` 또는 `125.0` 를 의미합니다.
* `1.25e-2` 는 `1.25 x 10의 -2승` 또는 `0.0125` 를 의미합니다.
`ext`의 지수를 갖는 16진법 숫자의 경우, 밑에 `2의 exp승`을 곱합니다:
- `0xFp2` 는 `15 x 2의 2승` 또는 `60.0`을 의미합니다.
* `0xFp-2` 는 `15 x 2의 -2승` 또는 `3.75`를 의미합니다.
아래의 모든 부동소수점 리터럴은 12.1875라는 10진법 값을 갖습니다:
``` swift
let decimalDouble = 12.1875
let exponentDouble = 1.21875e1
let hexadecimalDouble = 0xC.3p0
```

숫자 리터럴은 그것을 읽기 더 쉽게 만들기 위하여 추가적인 서식 설정을 포함할 수 있습니다. 정수와 소수 모두 가독성 측면을 돕기 위해 0이 추가로 붙거나 `_`를 포함할 수 있습니다. 두 종류의 서식 모두 리터럴의 근본 값에는 영향을 미치지 않습니다:
``` swift
let paddedDouble = 000123.456
let oneMillion = 1_000_000
let justOverOneMillion = 1_000_000.000_000_1
```
- - - -
## 단어 정리
- numeric (명) 수. 숫자.
- decimal 십진법의
- binary 이진법의
- octal 8진법의
- hexadecimal 16진법의
- exponent (수학) 지수
- base number (수학) 밑
- indicated  표시된. 명시된.
	- indicate 나타내다
- formatting 서식 설정
	- format 서식(을 만들다)
- underscore 밑줄 (`_`). = underline.
- underlying 밑에 있는. 근본적인.
- notation 표기법
	- decimal notation 십진법
- decimal point 소수점
- decimal float
> Decimal floats can also have an optional exponent, indicated by an uppercase or lowercase e; hexadecimal floats must have an exponent, indicated by an uppercase or lowercase p.  
