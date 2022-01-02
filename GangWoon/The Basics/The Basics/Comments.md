# Comments

Use comments to include nonexecutable text in your code, as a note or reminder to yourself. 

코드에서 실행시키질 않을 문자는 코맨트를 사용하세요, 노트 또는 너자신에게 알려줄 것들을



Comments are ignored by the Swift compiler when your code is compiled.

당신의 코드가 컴파일될 때 컴파일러는 코맨트를 무시할 겁니다.



Comments in Swift are very similar to comments in C. Single-line comments begin with two forward-slashes (`//`):

씨 커맨트와 스위프트 커맨트는 유사합니다. 두개 슬래쉬를 사용해서 싱글라인 코맨트를 사용할 수 있습니다.



Multiline comments start with a forward-slash followed by an asterisk (`/*`) and end with an asterisk followed by a forward-slash (`*/`):

멀티라인 코맨트는 슬래쉬 뒤 별표로 시작하고 별표슬래쉬로 끝을 표시합니다.



Unlike multiline comments in C, multiline comments in Swift can be nested inside other multiline comments. 

씨 멀티라인 코맨트와 달리 스위프트는 내부에 다른 멀티라인 코맨트를 사용할 수 있습니다.



You write nested comments by starting a multiline comment block and then starting a second multiline comment within the first block. 

내포된 커맨트를 작성한다. 멀티라인 코맨트 블럭을 시작하고 다시 두번째 멀티라인 코맨트를 시작한다 첫번째 블록 안에서



The second block is then closed, followed by the first block:

두번째 블록이 닫혔고, 따라오는 건 첫번째 블럭이다.



Nested multiline comments enable you to comment out large blocks of code quickly and easily, even if the code already contains multiline comments. ???

내포된 멀티 라인 커맨트는 쉽고 빠르게 코드의 큰 블럭을  주석처리할 수 있습니다. 비록 코드가 멀티라인 코맨트를 포함되어 있다 하더라도.





Nested: 중첩된

asterisk: 별표