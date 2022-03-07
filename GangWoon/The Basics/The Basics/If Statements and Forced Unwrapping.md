### If Statements and Forced Unwrapping

You can use an `if` statement to find out whether an optional contains a value by comparing the optional against `nil`. 

당신은 이프문을 사용해서 닐에 반하여 비교를 함으로써  값이 옵셔널을 포함했는지  찾을 수 있다.



You perform this comparison with the “equal to” operator (`==`) or the “not equal to” operator (`!=`).

당신은 같음  연산자 또는 같지 않음 연산자를 사용해서 이 비교를 수행할 수 있다.



If an optional has a value, it’s considered to be “not equal to” `nil`:

만약 옵셔널 값이 있다면, 닐과 같지 않다를 고려되어야한다.



Once you’re sure that the optional *does* contain a value, you can access its underlying value by adding an exclamation point (`!`) to the end of the optional’s name. 

당신이 옵셔널이 값이 포함되있다고 확힌한다면, 당신은 옵셔널 이름의 끝에 느낌표를 추가함으로써 기본값을 접근할 수 있다 



The exclamation point effectively says, “I know that this optional definitely has a value; please use it.” 

그 느낌표는 효과적으로 말한다. 나는 이 옵셔널이 명확하게 값이 있다는 걸 알아 이걸 그냥 사용해줘. <정신차리세요 제발>



This is known as *forced unwrapping* of the optional’s value:

이것은 옵셔널 값의 강제 언래핑으로 알려졌다.



For more about the `if` statement, see [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html).

더 많은 정보는 링크를 통해주세요



Trying to use `!` to access a nonexistent optional value triggers a runtime error. 

존재하지 않는 옵셔널 값을 강제 언래핑한다면 런테임 에러를 발생하는 트리거로 사용됩니다.



Always make sure that an optional contains a non-`nil` value before using `!` to force-unwrap its value.

값을 강제 언래핑을 하기전에 옵셔널이 닐이 아닌지 확인해주세요.



underlying: 기본

exclamation: 느낌표

