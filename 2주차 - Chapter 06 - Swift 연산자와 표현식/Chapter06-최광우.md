# Chapter06 스위프트 연산자와 표현식

## 스위프트의 표현식 구문
- 가장 기본적인 스위프트 표현식은 하나의 **연산자**, 두 개의 **피연산자**, **할당자**로 구성된다.
    - ex) ```var myResult = 1 + 2```
    - **+**연산자는 두 개의 피연산자를 더하는 데 사용된다. 할당 연산자**=**는 덧셈의 결과를 myResult라는 이름의 변수에 할당한다.

## 기본 할당 연산자
```Swift
var x: Int?     // 옵셔널 Int 변수 할당
var y = 10      // 두 번째 Int 변수 선언과 초기화

x = 10          // x에 값 할당
x = x! + y      // 언래핑한 x와 y의 합을 x에 저장
x = y           // y의 값을 x에 할당
```

## 산술 연산자
- Swift는 수학적 표현식을 생성하기 위하여 다양한 연산자를 제공한다. 대부분은 두 개의 피연산자를 받는 **이항 연산자**이다.
```Swift
var x = -10 // 단항 - 연산자는 변수 x에 -10을 할당하기 위해 사용함
x = x - 5 // 뺄셈 연산자. x에서 5를 뺌

/*
1. - (단항)  : 변수 또는 표현식의 값을 음수로 만듦
2. *        : 곱셈
3. /        : 나눗셈
4. +        : 덧셈
5. -        : 뺄셈
6. %        : 나머지 연산
*/
```

## 복합 할당 연산자
```Swift
/*
1. x += y   : x와 y를 더한 결과를 x에 저장한다.
2. x -= y   : x와 y를 뺀 결과를 x에 저장한다.
3. x *= y   : x와 y를 곱한 결과를 x에 저장한다.
4. x /= y   : x를 y로 나눈 결과를 x에 저장한다.
5. x %= y   : x를 y로 나눈 나머지를 x에 저장한다.
*/
```

## 비교 연산자
- **비교 연산자**는 프로그램 흐름 제어 로직을 만드는데 가장 많이 사용된다
```Swift
if x == y {
    // 작업 수행
}

/*
1. x == y
2. x > y
3. x >= y
4. x < y
5. x <= y
6. x != y
*/
```

## Boolean 논리 연산자
```Swift
var flag = true         // flag는 true이다.
var secondFlag = !flag  // secondFlag에는 false가 저장된다.

// OR(||) 연산자는 두 개의 피연산자 중 하나가 true라고 판단되면 true를 반환하고, 두 개의 피 연산자 모두 true가 아니라면 false를 반환한다.
if (10 < 20) || (20 < 10) {
    print("Expression is true")
}

// AND(&&) 연산자느 두 개의 피연산자 모두 true일 때만 true를 반환한다.
if (10 < 20) && (20 < 10) {
    print("Expression is true")
}
```

## 범위 연산자
```Swift
// 닫힌 범위 연산자
x...y // x부터 시작해서 y로 끝나는 숫자의 범위를 나타낸다.

// 반 개방 범위 연산자
x..<y // x부터 시작하는 모든 숫자를 포함하지만 y는 포함되지 않는다.

// 단방향 범위 연산자
x...
...y
// 범위 앞의 시작 또는 끝에 도달할 때ㅔ까지 지정된 범위 방향으로 최대한 확장할 수 있는 범위를 지정한다.
```

## 삼항 연산자
```Swift
let x = 10
let y = 20

print("Largest number is \(x > y ? x : y)") // x가 y보다 크면 x가 출력, 반대면 y가 출력된다.
```

## nil 병합 연산자
- **nil 병합 연산자(??)**를 사용하면 옵셔널에 nil 값이 있는 경우 디폴트 값을 사용할 수 있다.
```Swift
let customerName: String? = nil
print("Welcom back, \(customerName ?? "Customer")")

let customerName2: String? = "John"
print("Welcom back, \(customerName ?? "Customer")") // customerName2 변수의 값이 nil이 아니라면 언래핑되어 할당된 값이 표현된다.
```


