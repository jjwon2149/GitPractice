# 챕터 7 - 스위프트 제어 흐름

---
### 7.1 - 반복 제어 흐름
* 어떤 코드를 실행할지, 몇 번 수행 할지에 대한 결정 등 실행되는 프로그램 흐름을 통제하는 것을  ``제어흐름(control flow)``라고 한다
* 반복문은 조건에 만족할 때 까지 반복적으로 코드를 수행하는 구문이다
---
### 7.2 - 스위프트 for-in 구문
* for-in 반복문은 어떤 컬렉션이나 숫자 범위에 포함된 ``일련의 항목 들을 반복하는데 사용``한다.

```swift
for 상수명 in 컬렉션 또는 범위 {
    // 실행될 코드
}
```

```swift 
for index in 1...5 {
	print("Value of index is \(index)")
}
```

* for-in 반복문은 ``배열이나 딕셔너리`` 같은 컬렉션을 가지고 작업할때 유용하다.

```swift
var count = 0

//wildccard(와일드카드패턴)이라고 한다.
for _ in 1...5 {
	//현재 값에 대한 참조체가 필요없다. 
	count += 1
} 
```

### 7.2.1 - while 반복문
* while 반복문은 어떤 조건에 만족할 때까지 반복해야할때 사용한다.

```swift
while 조건문 {
	// 실행될 스위프트 구문
}
```

```swift 
var myCount = 0

while myCount < 100 {
	myCount += 1
}
```

---
### 7.3 - repeat … while 반복문
* repeat … while 반복문은 다른프로그래밍 언어에 있는 ``do-while 반복문과 비슷``하다.
* while문을  거꾸로 했다고 생각하면 이해하기 쉽다
* repeat … while 반복문은 언제나 ``적어도 한 번은 무조건 실행``된다.
* while 반복문 : ``조건문 평가 -> 코드 실행``
* repeat … while 반복문 : ``코드실행 -> 조건문 평가``

```swift
repeat {
	// 실행될 코드
} while 조건식
```

```swift
var i = 10

repeat {
	i -= 1
	print(i)
} while (i > 0)
```

---
### 7.4 - 반복문 빠져나오기
* 반복문을 만들었는데 무한반복이거나 네트워크 소켓을  활성화를 지속적으로 점검할때  사용 예
* 반복문을 빠져나오기 위해서는 ``break``구문을 사용한다

```swift
var j = 10

for _ in 0 ..< 100 {
	j += j

	if j > 100 {
		break
	}

	print("j = \(j)")
}
```

---
### 7.5 - continue 구문
* continue 구문은 반복문의 나머지 코드를 건너뛰고 반복문을 처음으로 다시 돌아가게 한다.

```swift
var i = 1

while i < 20 {
	i += 1

	if (i % 2 ) != 0 {
		continue
	}

	print("i = \(i)")
}
```

---
### 7.6 - 조건부 제어 흐름
---
### 7.7 - if 구문 사용하기
---
### 7.8 - if … else … 구문 사용하기
---
### 7.9 - if … else if … 구문 사용하기
---
### 7.10 - guard 구문
