# Chapter05 스위프트 데이터 타입, 상수 그리고 변수

## 날짜: ~04월 14일

## 5.2 스위프트 데이터 타입

### 정수형 데이터 타입

Signd 정수 - 양수, 음수, 0을 저장
UnSignd 정수 - 정수, 양수, 0을 저장

Swift는 8, 16, 32, 64비트 정수를 지원 (Int는 기본 64비트)

```swift
print("Int : \(Int.min)")
print("Int64 : \(Int64.min), \(Int64.max)")
print("Int32 : \(Int32.min), \(Int32.max)")
print("Int16 : \(Int16.min), \(Int16.max)")
print("Int8 : \(Int8.min), \(Int8.max)")
```

```
Int : -9223372036854775808
Int64 : -9223372036854775808, 9223372036854775807
Int32 : -2147483648, 2147483647
Int16 : -32768, 32767
Int8 : -128, 127
```

### 부동소수점 데이터 타입

Double, Float 타입

Double은 64비트의 부동소수점 수를 저장하기 위해 사용
Float은 32비트의 부동소수점 수를 저장하기 위해 사용

```swift
print(Double.pi) 
print(Float.pi)
```

```
3.141592653589793
3.1415925
```

### 불리언 데이터 타입
참과 거짓 1,0을 처리하는 데이터타입

```swift
var bool: Bool = true
```

### 문자 데이터 타입
하나의 문자를 저장하는 데이터 타입

### 문자열 데이터 타입
문자열은 일반적으로 단어나 문장을 구성하는 일련의 문자들이다.
```swift
let someString = "Some string literal value"

let quotation = """
The White Rabbit put on his spectacles.  "Where shall I begin,
please your Majesty?" he asked.

"Begin at the beginning," the King said gravely, "and go on
till you come to the end; then stop."
"""

let wiseWords = "\"Imagination is more important than knowledge\" - Einstein"
// "Imagination is more important than knowledge" - Einstein
let dollarSign = "\u{24}"        // $,  Unicode scalar U+0024
let blackHeart = "\u{2665}"      // ♥,  Unicode scalar U+2665
let sparklingHeart = "\u{1F496}" // 💖, Unicode scalar U+1F496
```
---

## 5.3 스위프트 변수
```swift
var value: Type  = 할당할 값
```


---

## 5.4 스위프트 상수
> If a stored value in your code won’t change, always declare it as a constant with the let keyword. Use variables only for storing values that change.
> 
> 코드에 저장된 값이 변경되지 않는 경우에는 항상 let 키워드를 사용하여 상수로 선언하세요. 변수는 변경되는 값을 저장할 때만 사용하세요.

한번 값을 할당하면 바꾸지 못하는 상수.

```swift
let value: Type  = 할당할 값
```


---


## 5.6 타입 애너테이션과 타입 추론

":" 기호를 사용해서 타입을 지정해 줄 수 있다
```swift
let intTypeValue: Int  = 5 
```

타입 애너테이션이 없다면 스위프트 컴파일러는 타입 추론을 하여 타입을 지정한다.
```swift
let value = "String"
print(type(of: value)) //String
```


---


## 5.7 스위프트 튜플
여러값을 하나의 항목으로 임시적으로 그루핑 하는 방법이다.
```swift
let http404Error = (404, "Not Found")
// http404Error is of type (Int, String), and equals (404, "Not Found")
```


---


## 5.8 스위프트 옵셔널 타입
> You use optionals in situations where a value may be absent. An optional represents two possibilities: Either there is a value of a specified type, and you can unwrap the optional to access that value, or there isn’t a value at all.
> 
> 값이 없을 수 있는 상황에서 옵셔널을 사용합니다. 옵셔널을은 두 가지 가능성을 나타냅니다: 지정된 유형의 값이 있고 옵션의 래핑을 해제하여 해당 값에 액세스할 수 있거나 값이 전혀 없는 경우입니다.

변수를 선언할 때 "?"문자를 두어 옵셔널이 되게 한다.


>You use optional binding to find out whether an optional contains a value, and if so, to make that value available as a temporary constant or variable. Optional binding can be used with if, guard, and while statements to check for a value inside an optional, and to extract that value into a constant or variable, as part of a single action.
>
>옵셔널 바인딩을 사용하여 옵셔널에 값이 포함되어 있는지 확인하고, 포함되어 있다면 해당 값을 임시 상수나 변수로 사용할 수 있도록 합니다. 선택적 바인딩은 if, guard 및 while 문과 함께 사용하여 단일 작업의 일부로 선택 사항 내부의 값을 확인하고 해당 값을 상수 또는 변수로 추출할 수 있습니다.

- 옵셔널 강제 언래핑
> When nil represents an unrecoverable failure, such as a programmer error or corrupted state, you can access the underlying value by adding an exclamation mark (!) to the end of the optional’s name. This is known as force unwrapping the optional’s value. When you force unwrap a non-nil value, the result is its unwrapped value. Force unwrapping a nil value triggers a runtime error
> 
> 프로그래머 오류나 손상된 상태 등 복구할 수 없는 실패를 나타내는 경우, 옵션 이름 끝에 느낌표(!)를 추가하여 기본값에 액세스할 수 있습니다. 이를 옵션 값 강제 래핑 해제라고 합니다. nil이 아닌 값을 강제로 래핑 해제하면 결과는 래핑 해제된 값입니다. nil 값을 강제로 언래핑하면 런타임 오류가 트리거됩니다.

```swift
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)


let number = convertedNumber!


guard let number = convertedNumber else {
    fatalError("The number was invalid")
}
```

옵셔널에 값이 할당되았다면 해당 값이 옵셔널 내에서 래핑 되었다고 말한다.

- 옵셔널 바인딩

```swift
if let actualNumber = Int(possibleNumber) {
    print("The string \"\(possibleNumber)\" has an integer value of \(actualNumber)")
} else {
    print("The string \"\(possibleNumber)\" couldn't be converted to an integer")
}
```

- 암묵적 언래핑
> You write an implicitly unwrapped optional by placing an exclamation point (String!) rather than a question mark (String?) after the type that you want to make optional. Rather than placing an exclamation point after the optional’s name when you use it, you place an exclamation point after the optional’s type when you declare it.
> 
> 이러한 종류의 옵션은 암시적으로 래핑 해제된 옵셔널으로 정의됩니다. 옵셔널으로 만들려는 유형 뒤에 물음표(문자열?)가 아닌 느낌표(문자열!)를 붙여 암시적으로 래핑되지 않은 옵셔널을 작성합니다. 옵셔널을 사용할 때 옵셔널이름 뒤에 느낌표를 붙이는 대신, 선언할 때 옵셔널의 유형 뒤에 느낌표를 붙입니다.
```swift
let possibleString: String? = "An optional string."
let forcedString: String = possibleString! // Requires explicit unwrapping


let assumedString: String! = "An implicitly unwrapped optional string."
let implicitString: String = assumedString // Unwrapped automatically
```


---

## 5.8 타입 캐스팅

부모 타입의 클래스로 변형하는것 -> 업캐스팅 as
자식 타입의 클래스로 변형하는것 -> 다운캐스팅 as?

### EX
UIkit에서 커스텀한 셀을 그릴때 경험
dequeueReusableCell을 사용할때 다운캐스팅을 해본적이 있을거임!
```swift
 let cell = timeTableView.dequeueReusableCell(withIdentifier: "customCell", for: indexPath) as! CustomTableViewCell
```
