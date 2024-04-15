# Chapter 05 - Swift 변수, 상수, 데이터 타입
        
## Swift 변수 & 상수
- **변수:** 앱이 사용하는 데이터를 저장하기 위해 예약된 컴퓨터 메모리 내의 위치, 변수에는 값을 할당할 수 있고, 할당한 값을 변경할 수 있다.
- **상수:** 변수와 기능은 같지만 할당한 값을 변경할 수 없는 특징이 있다.
    - 변수는 ```var variableName``` 상수는 ```let constantName```으로 표현 가능하다
```Swift
let tempString: String
tempString = "Temporary String"
// 위와 같이 값이 할당되지 않은 상수는 처음 한 번에 한해 값을 할당 할 수 있다.
```

## Swift의 데이터 타입

- **Int:** 정수형 데이터 타입으로 양수, 음수, 0을 저장할 수 있는 Int, 0과 양수만 저장 가능한 UInt로 나뉜다.
    - ex) Int8, Int16, Int32, Int64, UInt8, UInt16, UInt32, UInt64
    - 대부분 뒤에 숫자를 붙이는 형식이 아닌 Int를 사용하는 것이 가장 편리하고 일반적이지만, 특정한 상황에서는 다른 자료형이 필요할 수 있음.

- **Double & Float:** 소수점이 있는 값을 저장할 수 있는 데이터 타입
    - Double: 최대 64비트의 소수점 수를 저장 가능
    - Float: 최대 32비트의 소수점 수를 저장 가능

- **Boolean:** 참(true)/거짓(false)을 처리하는 데이터 타입
- **Character:** 문자, 숫자, 문장 부호, 기호와 같은 하나의 문자를 저장할 수 있는 데이터 타입
- **String:** 단어나 문장을 저장할 수 있는 데이터 타입
    - 표현방법:
        1. 문자열 보간 -> "\(stringVariable)"
        2. 삼중 따옴표 -> """문자열""" 형식으로 여러줄을 입력할 때 사용
        3. 특수 문자/이스케이프 시퀀스 -> "\n"(줄바꿈), "\r"(캐리지 리턴), "\t"(들여쓰기), "\\"(역슬래시 표현), "\""(쌍따옴표 표현), "\'"(홑따옴표 표현)
   
## Swift Tuple
- **튜플**은 여러 값을 하나의 항목으로 임시적으로 그루핑(grouping)하는 데이터 타입이다.
```Swift
// 타입을 따로 정해주지 않으면 여러 데이터 타입을 저장할 수 있다.
let tempTuple = (10, 432.433, "Temp String")

// 튜플의 index에 해당하는 값을 따로 변수에 추출 가능하다.
let (tempInt, tempFloat, tempString) = tempTuple // tempInt = 10

// 따로 타입을 정해주면 그 형식을 따라야 한다.
let typeTuple: (Int, String, Float) = (30, "String", 95.03)

// 튜플을 생성할 때 각 key를 변수에 할당 가능하다.
let keyTuple = (count: 10, length: 432.33, message: "Key Tuple") // keyTuple.count => 10
```

## Swift Optional
- **Optional**은 변수 또는 상수에 값이 할당되지 않은 상황을 안전하게 처리하기 위한 방식이다.
```Swift
// Optional 선언부, Optional로 선언하면 해당 변수는 데이터가 할당되거나 아무런 값도 할당되지 않을 수 있다. 
var index: Int?
index = 3
var treeArray: [String] = ["Oak", "Pine", "Yew", "Birch"]

if index == nil {
    // index에 값이 할당되어 있지 않다.
    print("index에 값이 없다.")
} else {
    // index에 값이 할당되어 있다.
    // 값이 할당되어 있으면 래핑(wrapping)되었다고 한다.
    // Optional 변수에 !를 붙여 강제 언래핑(unWrapping) 가능하다.
    // 강제 언래핑은 잘못하면 앱이 뻗어버릴수 있으니 주의..
    print(treeArray[index!])
    
    // Optional Binding을 이용해 임시 변수나 상수에 할당하여 사용할 수 있다.
    // if 구문 실행이 끝나면 이 `if let index`상수는 더이상 존재하지 않게 되어 동일한 이름을 사용해도 충돌하지 않는다.
    if let index = index {
        print(treeArray[index])    
    }
    
    // 아래처럼 축약해서 사용도 가능하다.
    if let index {
        print(treeArray[index])
    }
    
    // if구문에서 Optional Binding 후 ,로 조건문을 추가할 수 있다.
    if let tempIndex = index, tempIndex == 3 {
        print(tempIndex)
    }
}
```

## 타입 캐스팅, 타입 검사
- **타입 캐스팅(Type Casting)**은 형 변환이라고도 하며 컴파일러가 어떤 값의 특정 타입을 식별하지 못하는 경우 발생하는데, 메서드나 함수가 반환하는 값이 불명확하거나 예상되지 않을 때 사용된다.
> 타입 캐스팅은 책을 읽어보고 잘 이해가 되지 않아 나중에 작성해야겠다 ㅠㅠ
