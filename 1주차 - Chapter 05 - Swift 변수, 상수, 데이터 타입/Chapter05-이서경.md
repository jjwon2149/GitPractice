## Chapter 05 -  스위프트 데이터 타입, 상수, 그리고 변수
### 데이터 타입

**정수형 데이터 타입(Int)**
- signed(부호O) / unsigned(부호X)
- (U)Int8/16/32/64
- 애플은 Int를 사용하라고 권장

</br>

**부동소수점 데이터 타입**
- Float: 최대 32비트의 부동소수점 수 저장 / 적어도 6자리까지 표현 가능
- Float16: 16비트, 낮은 정밀도 but  더 나은 성능 제공
- Double: 최대 64비트의 부동소수점 수 저장 / 플랫폼에 따라 최소 15자리까지 표현 가능
</br>

**불리언 데이터 타입(Boolean)**
- 참(true) / 거짓(false)
</br>

**문자 데이터 타입(Character)**
- 문자, 숫자, 문장 부호, 기호 등 하나의 문자를 저장
- 유니코드의 코드포인트 이용 가능
</br>

**문자열 데이터 타입(String)**
- 단어나 문장을 구성하는 일련의 문자들
- 검색, 매칭, 연결, 수정 등 다양한 편집 기능
- 문자열 보간법: \\(변수명)
- `“””` : 여러 줄의 문자열 선언 시 사용
각 줄의 들여쓰기= (해당 줄 들여쓰기 칸 수) - (마지막 닫는 삼중 따옴표 들여쓰기 칸 수)
</br>

**이스케이프 시퀀스**
- 개행, 탭 또는 문자열 내에 특정 유니코드 값을 지정
- 역슬래시 사용
- 예시:
`\n` - 개행, 
`\r` - 캐리지 리턴, 
`\t` - 탭, 
`\\` - 역슬래시, 
`\”` , `\’` - 문자열 내부에서 쌍/홑따옴표 사용, 
`\u{nn}` - 한 바이트 유니코드 스칼라



---

### 상수(let)
- 데이터를 저장하기 위해 예약된 컴퓨터 메모리 내의 위치
- 할당된 값 변경 불가능


### 변수(var)
- 상수와 같으나 할당된 값 변경 가능

</br>

**상수/변수의 타입을 지정하는 방법**
1. 타입 애너테이션(type annotation)
```swift
var userCount: Int = 18
```
2. 타입 추론(type inference)
```swift
var signalStrength = 2.231
```
- 타입 애너테이션 없이 상수 선언할 경우 꼭 선언 시 값을 할당해야 함
- 타입 애너테이션을 사용하는 경우 나중에 값을 할당할 수 있음
- 제네릭 타입을 선언할 때에는 타입 추론 불가. 타입 매개변수의 타입을 직접 명시해줘야 함


---

### 튜플(tuple)

- 여러 값을 하나의 항목으로 임시적으로 그루핑
- 서로 다른 타입 저장 가능

```swift
let myTuple = (10, 432.433, “This is a String”)
```

- 인덱스 위치 참조하여 접근
- 튜플에 있는 값을 추출하여 변수/상수에 각각 할당 가능
```swift
let (myInt, myFloat, myString) = myTuple
var(myInt, _, myString) = myTuple
```
- 튜플 생성 시에 각 값을 변수에 할당할 수도 있음 → 저장된 값을 참조할 때 변수를 사용할 수 있게 됨


---


### 옵셔널 타입(?)
- 변수 / 상수에 값이 할당되지 않은 상황(nil) 처리
</br>

**옵셔널 언래핑 방법**
1. 강제 언래핑(!)
2. 옵셔널 바인딩: 임시 변수나 상수에 할당
```swift
if let/var constantName = optionalName { }
guard let constantName = optionalName { } else { }
```
- 옵셔널이 값을 가지고 있는지 확인 후, 있으면 그 값을 할당하고 코드 실행

* if-let 약식 구문 도입
`if let index { }` 사용 가능

- 조건식 포함 가능

```swift
if let pet1, pet2, petCount > 1 {
    print(pet1)
    print(pet2)
} else {
    print("insufficient pets")
}
```

3. 암묵적 언래핑
```swift
var index: Int!
```



---

### 타입캐스팅(as)

- 메서드나 함수가 반환하는 값이 불명확하거나 예상되지 않은 타입의 값인 경우 컴파일러에게 알려줌

```swift
let myValue = record.object(forKey: “comment”) as! String
```

→ object(forKey:)의 반환값을 String 타입으로 처리
</br>

**업캐스팅(as)**
- 특정 클래스 객체가 상위 클래스들 중의 하나로 변형
- 하위 클래스는 안전하게 업캐스팅될 수 있으므로 보장된 변환
</br>

**다운캐스팅(as!)**
- 어떤 클래스에서 그 클래스의 하위 클래스로 변환
- 강제 변환
- as?를 사용한 옵셔널 바인딩이 안전

```swift
if let myTextView = myScrollView as? UITextView {
    print("성공")
} else {
    print("실패")
}
```
  
</br>

### 타입 검사(is)
```swift
if myObject is MyClass { }
```

→ 해당 객체가 MyClass라는 클래스의 인스턴스인지 검사하는 코드


---
### 새로 알게 된 것
- 튜플의 값을 추출하여 각각의 변수와 상수에 할당할 수 있다.
- Swift 5.7부터 if let 약식 구문이 도입되어 임시 값을 꼭 사용하지 않아도 된다!
