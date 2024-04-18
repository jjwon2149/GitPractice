# 챕터 8 -  스위프트 switch 구문
----
## 8.1 - 왜 switch 구문을 사용하는가?
* 몇 가지 조건문에는 ``if … else if …``으로 충분하지만 두세개 이상의 조건식을 사용할 때는 코드를 작성하는데 시간도 많이 들고 읽기도 어려워지기 때문에 ``switch``구문을 사용한다

---
## 8.2 - switch 구문 사용하기

```swift
switch 표현식 {
	case 일치하는 값1:
		코드구문
	case 일치하는 값2:
		코드구문
	case 일치하는 값3, 일치하는 값4:
		코드구문
	default:
		코드구문
		break
}
```

```swift
let value = 4

switch (value) {
	case 0:
		print("zero")
	case 1:
		print("one")
	case 2: 
		print("two")
	case 3:
		print("three")
	case 4:
		print("four")
	case 5:
		print("five")
	default:
		print("Integer out of range")
		break
```

---
## 8.5 - switch 구문에서 범위 매칭하기

```swift
let temperature = 83

switch (temperature) {
	case 0...49: 
		print("Cold")
	case 50...79:
		print("Warm")
	case 80...110:
		print("Hot")
	default:
		print("Temperature out of range")
}
```

---
## 8.6 -  where 구문 사용하기

```swift
let temperature = 54

switch (temperature) {
	case 0...49 where temperature % 2 == 0:
		print("Cold and even")
	case 50...79 where temperatrue % 2 == 0:
		print("Warm and even")
	case 80...110 where temperature % 2 == 0:
		print("Hot and even")
	default:
		print("Temperature out of range or odd")
}
```


---
## 8.7 - fallthrough
* swift는 다른언어와 다르게``case 구문에 끝에 break를 쓸 필요가 없다.``
* fallthrough구문을 사용하면 ``switch 구현부에 예외상황 효과를 주어 실행 흐름이 그다음의 case 구문으로 계속 진행``하게 할수 있다.

```swift
let temperature = 54

switch (temperature) {
	case 0...49 where temperature % 2 == 0:
		print("Cold and even")
		fallthrough
	case 50...79 where temperatrue % 2 == 0:
		print("Warm and even")
		fallthrough
	case 80...110 where temperature % 2 == 0:
		print("Hot and even")
		fallthrough
	default:
		print("Temperature out of range or odd")
		break
}
```





