# Chapter07 스위프트 제어흐름

## 날짜: ~04월 18일

## for-in 구문
for-in 문은 범위에 포함된 일련을 항목들을 반복하는데 사용됨

~~~swift
for 상수명 in 범위 or 컬렉션 {
    //실행 코드
} 
~~~

---

## while 반복문
while 문은 지정된 조건에 만족할 때까지 일련의 작업을 반복한다. 
~~~swift
while 조건문 {
    //실행 코드
}
~~~

---

## repeat while 반복문
repeat while 문은 지정된 조건에 만족할 때까지 일련의 작업을 반복한다. 실행코드를 실행 한 후 조건문을 검사한다.
~~~swift
repeat {
    //실행 코드
} while 조건식
~~~

---

## continue 구문
continue 구문은 반복문의 나머지 코드를 건너뛰고 반복문의 처음으로 다시 돌아가게 한다.
~~~swift
while 조건문 {
    //실행 코드
    if 조건문 {
        continue
    }
    print("Hello world")
}
~~~
if문에 들어가게 된다면 "Hello world"출력을 건너 뛰고 다음 반복문으로 가게 된다.

---

## if else 구문
조건식이 true로 판단되면 {}안의 코드블럭이 실행되게 된다.
~~~swift
if 조건식1 {
    //실행 코드
} else if 조건식2 {
    //실행 코드
} else {
    //조건식 1,2가 false일때 실행 코드
}
~~~

---

## guard 구문
guard 구문은 if 구문과 유사하지만 조건식이 false일때 실행되어야 하는 else 블럭이 반드시 포함되어야 한다.

~~~swift
guard 조건문(불리언) else {
    //종료 구문    
}
~~~

~~~swift
func multiplyByTen(value: Int?) {
    guard let number = value, number < 10 else {
        print("Number is too high")
        return
    }
    let result = number * 10
    print(result)
}
multiplyByTen(value: 5)
multiplyByTen(value: 10)
~~~
guard 구문에 언래핑된 number는 if문과 다르게 코드밖에서도 유효하다.

---