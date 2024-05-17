# 07Chapter_이상민

## for-in 구문
for-in 반복문은 어떤 컬렉션이나 숫자 범위에 포함된 일련의 항목들을 반복하는 데 사용되며, 사용하기 쉬운 반복문 옵션을 제공한다.
```
for 상수명 in 컬렉션 또는 범위{
    실행될 코드
}
```
<예제>

```
for index in 1...5{
    print("Value of index is \(index)")
}

//출력
Value of index is 1
Value of index is 2
Value of index is 3
Value of index is 4
Value of index is 5
```
상수명을 반드시 선언해야 하는 것은 아니다.
```
var count = 0

for _ in 1...5{
    count += 1
}
```
## while 반복문
for 반목문은 프로그램 내에서 몇 번 반복해야 하는지 알고 있을 때 유용하다. 하지만, 어떤 조건에 만족할 때까지 반복해야 하는 코드가 있는데 그 조건을 충족할 때 까지 몇 번을 반복해야 하는지를 알 수 없는 경우에 while반복문을 사용한다.
```
while 조건문{ //조건문은 true 또는 false를 반환하는 표현식
    실행될 스위프트 구문
}

<예제>
var myCount = 0

while myCount < 100{
    myCount += 1
}
```

## repeat ... while 반복문
**repeat ... while 반복문은 반드시 반복문 안의 코드가 언제나 적어도 한 번은 실행되야 하는 상황을 위해 사용된다.**

```
repeat{
    여기에 스위프트 구문이 온다.
}while 조건식

<예제>
var i = 0

repear{
    i-= 1
}while(i > 0)
```

## 반복문에서 빠져나오기(break)
반복문을 만들었는데 반복문이 종료되는 조건에 만족하기 전에 어떤 조건에서 반복문을 빠져나와야 할 경우가 있다. 특히 무한 반복을 만들었을 경우가 그러하다.
<예시> 네트워크 소켓의 활성화를 지속적으로 점검해야할 경우
```
var j = 10

for _ in 0..<100{
    j += j

    if j > 100{
        break //빠져나오기
    }

    print("j = \(j)")
}
```

## continue
continue 구문은 반복문의 나머지 코드를 건너뛰고 반복문의 처음으로 다시 돌아가게 한다.
```
var i = 1

whild i < 20{
    i += 1

    if (i % 2) != 0{
        continue
    }
    print("i = \(i)")
}
```

## if 구문 사용하기
```
if 조건식{
    조건식이 true일 때 수행될 스위프트 코드
}

<예제>
let x = 10
if x > 9{
    print("x is greater than 9!")
}
```

## if ... else ... 구문 사용하기
변형된 if 구문은 if 구문의 조건식이 false로 판단될 때 수행할 코드를 지정할 수 있게 해준다.
```
if 조건식{
    //조건식이 true일 때 수행될 스위프트 코드
}else{
    ///조건식이 false일 때 수행될 스위프트 코드
}

<에제>
let x = 10
if x > 9{
    print("x is greater than 9!")
}else{
    print("x is less than 9!")
}
```

## if ... else if ... 구문 사용하기
디양한 조건을 바탕으로 결정해야 할 때 사용한다.
```
let x = 9
if x == 10{
    print("x is 10)
}else if x== 9{
    print("x is 9")
}else if x == 8{
    print("x is 8)
}
```

## guard 구문
guard 구문은 불리언 표현식을 포함하며, true일 때만 guard 구문 다음에 위치한 코드가 실행된다. guard 구문은 불리언 표현식이 false일 때 수행될 else 절을 반드시 포함해야 한다. else 절의 코드는 바드시 현재의 코드 흐름에서 빠져나가는 구문(return, break, continue, throw 등)을 포함해야 한다.

```
guard <조건문(부리언 표현식)> else{
    조건문이 false일 때 실행될 코드
    <종료구문>
}

<예제>
func multiplyByTen(value: Int?){
    guard let number = value, number < 10 else{
        print("Numbe is too hight)
        return
    }

    let result = number * 10
    print(result)
}

multiplyByten(value: 5)
multiplyByTen*(value: 10)
```

### 배운점
repeat ... while 반복문의 경우 자주 사용하지 않아서 잊고 있었는데, 공부하면서 repeat ... while 반복문에 대해 다시 배울 수 있었다.