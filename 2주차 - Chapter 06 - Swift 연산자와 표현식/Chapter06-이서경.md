## Chapter 06 -  스위프트 연산자와 표현식
### 불리언 논리 연산자
- OR(||) 연산자: 두 피연산자 중 하나라도 true면 true 반환
- AND(&&) 연산자: 두 피연산자 모두 true일 때맨 true 반환
</br>

### 범위 연산자
```swift
// 1. 닫힌 범위 연산자(x부터 y까지)
x...y
// 2. 반개방 범위 연산자(x이상 y미만)
x..<y
// 3. 단반향 범위 연산자(그 범위 앞의 시작 또는 끝에 도달할 때까지)
x...
...y
```
</br>

### 삼항 연산자
조건문 ? 참인 경우의 표현식 : 거짓인 경우의 표현식
</br>

### nil 병합 연산자
옵셔널에 nil 값이 있는 경우 디폴트 값 사용 가능

```swift
let customerName: String? = nil
print("Welcome back, \(customerName) ?? "customer")")
// customer 출력
```
</br>

### 비트 연산자
- NOT(~)
- AND(&)
- OR(|)
- XOR(^): 두 개의 비트 중 하나만 1일 경우에만 1
- 왼쪽 시프트 비트 연산(<<): 지정된 횟수만큼 왼쪽으로 이동 후, 오른쪽의 빈자리는 0으로 채움. 한 자리씩 이동하면 정숫값은 두 배가 됨.
```swift
let z = x << 1
```
- 오른쪽 시프트 비트 연산(>>): 지정된 횟수만큼 오른쪽으로 이동시킨 후 마지막 비트는 폐기함. 최상위 비트 값은 부호비트 설정 여부에 따라 결정됨. 한 자리씩 이동하면 정숫값은 절반이 됨.
```swift
let z = x >> 1
```

산술연산자와 마찬가지로 비트 연산한 결과를 바로 할당하는 연산자 사용 가능 (ex. ^=)
