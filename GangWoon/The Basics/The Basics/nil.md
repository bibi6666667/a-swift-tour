### nil

You set an optional variable to a valueless state by assigning it the special value `nil`:

당신은 옵셔널 값이 값이 없는 상태는 닐이라는 특별한 값을 셋한다.



You can’t use `nil` with non-optional constants and variables. 

당신은 옵셔널이 아닌 상수나 변수에 닐을 할당할 순 없다.



If a constant or variable in your code needs to work with the absence of a value under certain conditions, always declare it as an optional value of the appropriate type.

만약 당신이 작성한 상수 또는 변수가 몇가지 상황에서 값의 부재를 갖을 필요가 있다면, 항상 적절한 타입의 옵셔널 값으로 선언하세요.



If you define an optional variable without providing a default value, the variable is automatically set to `nil` for you:

당신이 기본 값을 제공하지 않고  옵셔널 변수를 정의한다면, 그 변수는 자동적으로 닐이 셋이 된다.



Swift’s `nil` isn’t the same as `nil` in Objective-C. In Objective-C, `nil` is a pointer to a nonexistent object. 

스위프트의 닐은 오브젝티브 씨의 닐과 동일하지 않다. 오브젝티브 씨 닐은 객체가 존재하지 않는 포인터를 의미한다.



In Swift, `nil` isn’t a pointer—it’s the absence of a value of a certain type. 

스위프트에서는 포인터가 아니다. 이것은 특정 타입의 값의 부재를 의미한다.



Optionals of *any* type can be set to `nil`, not just object types.

애니 타입의 옵셔널은 닐로 셋할 수 있다. 객체 타입 뿐만아니라







