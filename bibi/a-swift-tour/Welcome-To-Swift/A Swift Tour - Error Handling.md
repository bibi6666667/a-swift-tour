# A Swift Tour - Error Handling

> You represent errors using any type that adopts the `Error` protocol.
>
> ``` swift
> enum PrinterError: Error {
>     case outOfPaper
>     case noToner
>     case onFire
> }
> ```
>
> Use `throw` to throw an error and `throws` to mark a function that can throw an error. If you throw an error in a function, the function returns immediately and the code that called the function handles the error.
>
> ``` swift
> func send(job: Int, toPrinter printerName: String) throws -> String {
>     if printerName == "Never Has Toner" {
>         throw PrinterError.noToner
>     }
>     return "Job sent"
> }
> ```
>
> There are several ways to handle errors. One way is to use `do`-`catch`. Inside the `do` block, you mark code that can throw an error by writing `try` in front of it. Inside the `catch` block, the error is automatically given the name `error` unless you give it a different name.
>
> ``` swift
> do {
>     let printerResponse = try send(job: 1040, toPrinter: "Bi Sheng")
>     print(printerResponse)
> } catch {
>     print(error)
> }
> // Prints "Job sent"
> ```
>
> > EXPERIMENT
> >
> > Change the printer name to `"Never Has Toner"`, so that the `send(job:toPrinter:)` function throws an error.
>
> You can provide multiple `catch` blocks that handle specific errors. You write a pattern after `catch` just as you do after `case` in a switch.
>
> ``` swift
> do {
>     let printerResponse = try send(job: 1440, toPrinter: "Gutenberg")
>     print(printerResponse)
> } catch PrinterError.onFire {
>     print("I'll just put this over here, with the rest of the fire.")
> } catch let printerError as PrinterError {
>     print("Printer error: \(printerError).")
> } catch {
>     print(error)
> }
> // Prints "Job sent"
> ```
>
> > EXPERIMENT
> >
> > Add code to throw an error inside the `do` block. What kind of error do you need to throw so that the error is handled by the first `catch` block? What about the second and third blocks?
>
> Another way to handle errors is to use `try?` to convert the result to an optional. If the function throws an error, the specific error is discarded and the result is `nil`. Otherwise, the result is an optional containing the value that the function returned.
>
> ``` swift
> let printerSuccess = try? send(job: 1884, toPrinter: "Mergenthaler")
> let printerFailure = try? send(job: 1885, toPrinter: "Never Has Toner")
> ```
>
> Use `defer` to write a block of code that’s executed after all other code in the function, just before the function returns. The code is executed regardless of whether the function throws an error. You can use `defer` to write setup and cleanup code next to each other, even though they need to be executed at different times.
>
> ``` swift
> var fridgeIsOpen = false
> let fridgeContent = ["milk", "eggs", "leftovers"]
> 
> func fridgeContains(_ food: String) -> Bool {
>     fridgeIsOpen = true
>     defer {
>         fridgeIsOpen = false
>     }
> 
>     let result = fridgeContent.contains(food)
>     return result
> }
> fridgeContains("banana")
> print(fridgeIsOpen)
> // Prints "false"
> ```
>
> 



## 에러 처리

`Error` 프로토콜을 채택하는 어떤 타입이든 사용하여 에러를 나타낼 수 있습니다.

``` swift
enum PrinterError: Error {
    case outOfPaper
    case noToner
    case onFire
}
```

에러를 던지기 위해 `throw`를, 그리고 에러를 던질 수 있는 함수를 표시하기 위해 `throws`를 사용하십시오. 만약 함수에서 에러를 던진다면, 그 함수는 즉시 반환되며 그 함수를 호출한 코드에서 에러를 다루게 됩니다.

``` swift
func send(job: Int, toPrinter printerName: String) throws -> String {
    if printerName == "Never Has Toner" {
        throw PrinterError.noToner
    }
    return "Job sent"
}
```

에러를 다루기 위한 몇 가지 방법이 있습니다. 하나는 `do-catch` 를 사용하는 것입니다. `do` 블럭 내에서, `try`를 앞에 작성함으로써 에러를 던질 수 있는 코드를 표시합니다. `catch`블럭 내에서, 에러는 다른 이름을 주지 않는 이상 자동적으로 `error`라는 정해진 이름 됩니다.

``` swift
do {
    let printerResponse = try send(job: 1040, toPrinter: "Bi Sheng")
    print(printerResponse)
} catch {
    print(error)
}
// Prints "Job sent"
```

> 실험
>
> `send(job:toPrinter:)`함수가 에러를 던지도록 프린터의 이름을 "Never Has Toner"로 바꿔 보십시오.

특정 에러를 다루기 위해 여러 개의 `catch` 블럭을 사용할 수 있습니다. switch문에서 `case`뒤에 패턴을 사용하는 것처럼, `catch`뒤에도 패턴을 사용할 수 있습니다.

```swift
do {
    let printerResponse = try send(job: 1440, toPrinter: "Gutenberg")
    print(printerResponse)
} catch PrinterError.onFire {
    print("I'll just put this over here, with the rest of the fire.")
} catch let printerError as PrinterError {
    print("Printer error: \(printerError).")
} catch {
    print(error)
}
// Prints "Job sent"
```

> 실험
>
> `do` 블럭 내에 에러를 던지는 코드를 추가해 보십시오. 에러가 첫 번째 catch블럭에서 처리되기 위해 어떤 에러를 던져야 합니까? 두 번째와 세 번째 블럭은 어떠합니까?

에러를 처리하는 또 다른 방법은 결과를 옵셔널로 바꾸기 위해 `try?`를 사용하는 것입니다. 만약 함수가 에러를 던진다면, 특정 에러는 버려지며 그 결과는 nil이 됩니다. 그렇지 않다면, 그 결과는 함수가 반환한 값을 담은 옵셔널이 됩니다.

``` swift
let printerSuccess = try? send(job: 1884, toPrinter: "Mergenthaler")
let printerFailure = try? send(job: 1885, toPrinter: "Never Has Toner")
```

함수가 반환되기 직전에, 모든 다른 코드가 실행된 다음 실행되는 코드 블럭을 작성하기 위해 `defer`를 사용하십시오. 이 코드는 그 함수가 에러를 던지는지 여부와 관계없이 실행됩니다. 당신은 심지어 그것들이 다른 시점에 실행되어야 하더라도, 설정 및 정리 코드를 나란히 작성하기 위해 `defer`를 사용할 수 있습니다, 

``` swift
var fridgeIsOpen = false
let fridgeContent = ["milk", "eggs", "leftovers"]

func fridgeContains(_ food: String) -> Bool {
    fridgeIsOpen = true
    defer {
        fridgeIsOpen = false
    }

    let result = fridgeContent.contains(food)
    return result
}
fridgeContains("banana")
print(fridgeIsOpen)
// Prints "false"
```







## 단어정리

- error handling 오류 처리
- represent 대표하다. 해당하다.
- discard 버리다
- defer 미루다. 연기하다. ...의 결정을 맡기다. (컴)
  - defer to sth : sth를 따르다. 좇다.
- setup 설정
- cleanup 청소
- next to each other 서로 바로 옆에. = 나란히.
- so that (목적)..하도록.

