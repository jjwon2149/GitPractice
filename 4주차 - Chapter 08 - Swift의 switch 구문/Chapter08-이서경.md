## 스위프트의 switch 구문
적은 수의 조건을 만들 땐 if ... else if ... 구문도 충분하지만, 조건이 많아질수록 코드 작성 시간도 많이 걸리고 읽기도 어려워지기 때문에 switch 구문을 사용

```swift
switch (표현식) {
    case 일치하는 값1:
        코드 구문
    case 일치하는 값2:
        코드 구문
    case 일치하는 값3, 일치하는 값4: // 공통으로 묶을 수 있음
        코드 구문
    default: // 일치하는 case 구문 없을 때
        코드 구문
}
```
- case를 공통으로 묶을 수 있음
- 일치하는 case 구문이 없을 경우를 위해 default 구문을 작성해줘야 함
</br>

```swift
let temperature = 10

switch (temperature)
{
    case 0...49 where temperature % 2 == 0:
        print("Cold and even")
        fallthrough
        // fallthrough 키워드 밑에 작성한 코드는 실행되지 않고 다음 case 구문으로 넘어감
    
    case 50...79 where temperature % 2 == 0:
        print("Warm and even")
        fallthrough
    
    case 80...110 where temperature % 2 == 0:
        print("Hot and even")
        fallthrough
    
    default:
    print("Temperature out of range or odd")
}
```
- case 구문에 범위 매칭 가능 (..., ..< 등)
- 부가적인 조건을 위해 where 구문 사용 가능
- fallthrough를 사용하면 그 다음 case 구문까지 실행
- 스위프트의 switch 구문에서 break는 거의 사용되지 않지만, default에서 아무런 작업도 할 필요가 없는 경우에 유용함

---
### 알게 된 점
fallthrough 키워드 밑에 작성한 코드는 실행되지 않고 다음 case로 넘어간다!
스위프트의 switch 구문에서 break는 거의 사용되지 않는다
