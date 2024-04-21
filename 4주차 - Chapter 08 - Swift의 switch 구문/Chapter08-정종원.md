# Chapter07 스위프트 switch 구문

## 날짜: ~04월 21일

## 왜 switch 구문을 사용하나??
if 문으로 여러개의 조건식을 만들땐 시간, 이해가 오래걸린다. 따라서 switch구문을 작성한다.

---

## switch 구문
~~~swift
switch 표현식 {
    case 일치하는 값:
    //실행 코드
    case 일치하는 값:
    //실행 코드
    default:
    //모든 case가 아닐때의 실행 코드
}
~~~

## switch 구문 + where 절
where 구문은 case 구문에 부가적인 조건을 추가하기 위해서 사용될 수 있다.

~~~swift
let temprature = 54
switch (temprature) {
    case 0...49 where temprature % 2 == 0:
        print("추워요..")
}
~~~
temprature가 0~49일 경우와 짝수일 경우를 판단한다.

## fallthrough
다른 언어와 다르게 swift에서의 switch 구문은 case에 적합하다면 자동으로 구문 밖으로 빠져나가게 된다.
하지만 fallthrough문을 사용하여 다음 case문으로 이동할 수 있게 된다.

~~~swift
let temprature = 54
switch (temprature) {
    case 0...49 where temprature % 2 == 0:
        print("추워요..")
        fallthrough
    case 50...79 where temprature % 2 == 0:
        print("따듯해요..")
        fallthrough
    ...
}
~~~
