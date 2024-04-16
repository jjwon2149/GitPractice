# Chapter06 스위프트 연산자와 표현식

## 날짜: ~04월 16일

## 6.1 표현식 구문

가장 기본적인 스위프트 표현식은 하나의 연산자와 두개의 피연산자, 할당자로 구성된다.
~~~swift
var myresult = 1 + 2
~~~
---
## 6.2 기본할당 연산자

```swift
let a = 10 // 대입연산자
```

---
## 6.3 산술 연산자

```swift
1 + 2
5 - 3
2 * 3
10.0 / 2.5
```

---
## 6.4 [복합 할당 연산자](https://developer.apple.com/documentation/swift/operator-declarations)

```swift
x += y
x -= y
x *= y
x /= y
x %/ y
```

---
## 6.5 비교 연산자

비교 연산자는 결과에 따라 불리언 결과를 반환한다
```swift
1 == 1   // true because 1 is equal to 1
2 != 1   // true because 2 isn't equal to 1
2 > 1    // true because 2 is greater than 1
1 < 2    // true because 1 is less than 2
1 >= 1   // true because 1 is greater than or equal to 1
2 <= 1   // false because 2 isn't less than or equal to 1
```
---
## 6.6 불리언 논리 연산자

비교 연산자는 결과에 따라 불리언 결과를 반환한다

 NOT (!a)

 AND (a && b)

 OR (a || b)

```swift
var a: Bool = true
var b: Bool = false

print(!a) // false
print(a && b) // false
print(a || b) // true

```

---
## 6.7 범위 연산자

### 닫힌 범위 연산자
for문에서 1...5와 같음 (1부터 5까지)
```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
```
### 반개방 범위 연산자
for문에서 1..<5와 같음 (1부터 4까지)
```swift
for index in 1..<5 {
    print("\(index) times 5 is \(index * 5)")
}
```

### 단방향 범위 연산자

x... -> x부터 범위 끝까지

---

## 6.8 삼항 연산자

a > 5 의 조건문이 참(true)를 반환한다면 a! false를 반환한다면 b
```swift
a > 5 ? a! : b
```
---

## 6.9 nil 병합 연산자

a가 nil이 아닌경우 a안의 래핑된 값에 접근하기 위해 a!한다
a가 nil일 경우 b를 반환한다
```swift
a != nil ? a! : b

```
---

## 6.10 비트 연산자

### NOT 비트 연산
NOT 비트 연산자 (~) 숫자의 모든 비트를 반전합니다.
```swift
let initialBits: UInt8 = 0b00001111
let invertedBits = ~initialBits  // equals 11110000
```

### AND 비트 연산
AND 비트 연산자 (&) 두 숫자의 비트를 결합합니다.
```swift
let firstSixBits: UInt8 = 0b11111100
let lastSixBits: UInt8  = 0b00111111
let middleFourBits = firstSixBits & lastSixBits  // equals 00111100
```

### OR 비트 연산
OR 비트 연산자 (|) 두 숫자의 비트를 비교합니다.
```swift
let someBits: UInt8 = 0b10110010
let moreBits: UInt8 = 0b01011110
let combinedbits = someBits | moreBits  // equals 11111110
```

### XOR 비트 연산
XOR 비트 연산자 (^) 두 숫자의 비트를 비교합니다.
입력한 비트가 같으면 1 다르면 0을 반환합니다
```swift
let firstBits: UInt8 = 0b00010100
let otherBits: UInt8 = 0b00000101
let outputBits = firstBits ^ otherBits  // equals 00010001
```

### XOR 비트 연산
XOR 비트 연산자 (^) 두 숫자의 비트를 비교합니다.
입력한 비트가 같으면 1 다르면 0을 반환합니다
```swift
let firstBits: UInt8 = 0b00010100
let otherBits: UInt8 = 0b00000101
let outputBits = firstBits ^ otherBits  // equals 00010001
```

### 왼쪽/오른쪽 시프트 비트 연산
비트 왼쪽 이동 연산자 (<<)와 비트 오른쪽 이동 연산자 (>>)는 아래의 정의된 규칙에 따라 특정 숫자만큼 왼쪽 또는 오른쪽으로 숫자의 모든 비트를 이동합니다.
```swift
let shiftBits: UInt8 = 4   // 00000100 in binary
shiftBits << 1             // 00001000
shiftBits << 2             // 00010000
shiftBits << 5             // 10000000
shiftBits << 6             // 00000000
shiftBits >> 2             // 00000001
```

---
