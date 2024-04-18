## 스위프트의 제어 흐름
### 반복 제어 흐름

**For-in 반복문**
```swift
for 상수명 in 컬렉션 또는 범위 {
    // 실행될 코드
}
```
- 현재 항목에 대한 참조체가 필요없을 땐 상수명 대신 _ 로 대체 가능
</br>

**while 반복문**
```swift
while 조건문 {
    // 실행될 코드 (조건문이 true인 동안 실행)
}
```
- 반복문 안의 코드를 실행하기 전에 표현식을 평가
- false라고 판단되면 반복문 안의 코드를 실행하지 않음
</br>

**repeat ... while 반복문**
```swift
repeat {
     // 실행될 코드
} while 조건식
```
- 반복문 안의 코드가 적어도 한 번은 실행되어야 하는 상황을 위해 사용
</br>

**break**
- 반복문에서 빠져나오는 키워드
</br>

**continue**
```swift
var i = 1

while i < 20 {
    i += 1
    
    if (i % 2) != 0 {
        continue
    }
    
    print("i = \(i)")
}
```
- 반복문의 나머지 코드를 건너뛰고 반복문의 처음으로 다시 돌아감
- i의 값을 2로 나눈 나머지가 있으면 print 호출 건너뜀
</br>

### 조건부 제어 흐름
**if ... else ... 구문**
```swift
if 조건식 {
    // true일 때 실행
} else {
    // false일 때 실행
}
```
</br>

**if ... else if ... 구문**
```swift
let x = 9

if x == 10 {
    print("x is 10")
} else if x == 9 {
    print("x is 9")
} else if x == 8 {
    print("x is 8")
}
```
- 여러 조건을 두어 사용할 수 있음
</br>

**guard 구문**
```swift
guard 조건문(불리언 표현식) else {
    // 조건문이 false일 때 실행될 코드
    종료 구문
}
// 조건문이 true일 때 실행될 코드
```
- else절의 코드는 반드시 현재 코드 흐름에서 빠져나가는 구문(return, break, continue, throw 등) 필요
