#  A Swift Tour - Simple Values (2)

> There’s an even simpler way to include values in strings: Write the value in parentheses, and write a backslash (`\`) before the parentheses. For example:
>
> ``` swift
> let apples = 3
> let oranges = 5
> let appleSummary = "I have \(apples) apples."
> let fruitSummary = "I have \(apples + oranges) pieces of fruit."
> ```
>
> > EXPERIMENT
> >
> > Use `\()` to include a floating-point calculation in a string and to include someone’s name in a greeting.
>
> Use three double quotation marks (`"""`) for strings that take up multiple lines. Indentation at the start of each quoted line is removed, as long as it matches the indentation of the closing quotation marks. For example:
>
> ``` swift
> let quotation = """
> I said "I have \(apples) apples."
> And then I said "I have \(apples + oranges) pieces of fruit."
> """
> ```
>
> Create arrays and dictionaries using brackets (`[]`), and access their elements by writing the index or key in brackets. A comma is allowed after the last element.
>
> ``` swift
> var shoppingList = ["catfish", "water", "tulips"]
> shoppingList[1] = "bottle of water"
> 
> var occupations = [
>     "Malcolm": "Captain",
>     "Kaylee": "Mechanic",
> ]
> occupations["Jayne"] = "Public Relations"
> ```
>
> Arrays automatically grow as you add elements.
>
> ``` swift
> shoppingList.append("blue paint")
> print(shoppingList)
> ```
>
> To create an empty array or dictionary, use the initializer syntax.
>
> ``` swift
> let emptyArray: [String] = []
> let emptyDictionary: [String: Float] = [:]
> ```
>
> If type information can be inferred, you can write an empty array as `[]` and an empty dictionary as `[:]`—for example, when you set a new value for a variable or pass an argument to a function.
>
> ``` swift
> shoppingList = []
> occupations = [:]
> ```

---

## 단순한 값 (2)

문자열에 값을 포함하기 위한 더욱 간단한 방법이 있습니다 : 소괄호 안에 값을 적고, 소괄호 앞에 백슬래시(`\`)를 적으십시오. 예를 들어 :

```swift
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```

> 실험
>
> 문자열 안에서 부동소수점 계산을 포함하기 위해, 그리고 인사에 누군가의 이름을 포함하기 위해 `\()`를 사용해 보십시오.
>
> ``` swift
> let version = 10.0
> let tinyUpdate = 0.1
> let name = "bibi"
> let greeting = "Hello \(bibi), this program is \(version + tinyUpdate) version."
> ```

여러 줄을 차지하는 문자열에 대해서는 세 큰따옴표(`"""`)를 사용하십시오. 닫는 따옴표의 들여쓰기와 맞을 때까지, 각 인용된 줄 앞의 들여쓰기는 삭제됩니다. 예를 들어 :

``` swift
let quotation = """
I said "I have \(apples) apples."
And then I said "I have \(apples + oranges) pieces of fruit."
"""
```

대괄호(`[]`)를 이용해 배열과 딕셔너리를 만들고, 인덱스나 키를 대괄호 안에 적음으로써 그것들의 원소에 접근하십시오. 마지막 원소 뒤에 콤마는 허용됩니다.

``` swift
var shoppingList = ["catfish", "water", "tulips"]
shoppingList[1] = "bottle of water"

var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```

배열은 당신이 원소를 추가할 때 마다 자동으로 늘어납니다.

``` swift
shoppingList.append("blue paint")
print(shoppingList)
```

빈 배열이나 딕셔너리를 만들기 위해서는, 초기화 구문을 사용하십시오.

``` swift
let emptyArray: [String] = []
let emptyDictionary: [String: Float] = [:]
```

타입 정보가 추론될 수 있다면, 빈 배열은 `[]`로, 빈 딕셔너리는 `[:]`로 작성할 수 있습니다 - 예를 들어, 변수를 위한 새 값을 설정할 때나 함수에 전달인자를 전달할 때.

``` swift
shoppingList = []
occupations = [:]
```



---

## 영단어 정리

- parentheses 괄호. 특히 소괄호 () 의 복수형
  - parenthesis 단수형 표현
- bracket 괄호. 특히 대괄호 [].
  - square brackets 대괄호 []
  - curly brackets 중괄호 {}
  - round brackets 소괄호 ()
- brace 괄호. 특히 중괄호 {}.
- greeting 인사. 
- quotation marks 따옴표 ''
  - double quotation marks 큰따옴표 ""
- indentation 들여 쓴 자리
  - indent 들여쓰기 / 들여쓰다
- quoted 인용된
- take up sth ...를 차지하다 (시간/공간)
- as long as ... 하는 한. ...하는 동안은.
- parameter (컴) 매개변수. variable에 해당
- argument (컴) 전달인자. value에 해당함

