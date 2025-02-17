#  챕터 5 -  스위프트 데이터 타입: 상수, 그리고 변수 #


* 2014년 6월 WWDC에서 iOS8 발표와 함께 Objective-C를 대신하는 언어로 발표된 Swift
  * Safe(안전한), Fast(신속한), Expressive(표현이 풍부하다)
  * 타입추론, 타입 제한을 통한, 안정성과, 메모리 자동 관리
  * 실행속도가 빠르다(LVVM-컴파일러)
  * 최근 현대적 언어들의 장점을 받아들여 읽기 쉽고 작성하기가 쉽다
---
* Swift 관련 문서 자료
  * https://developer.apple.com/documentation/swift
  * https://swift.org/about
  * https://bbiguduk.gitbook.io/swift
  * http://xho95.github.io/swift/programming/language/grammar/2017/02/28/The-Swift-Programming-Language.html
---
- 스위프트 데이터 타입
  - 정수(Interger)형 데이터(8,16,32, 64비트 지원)
    - Int ( 0을 포함한 음수,양수)
    - UInt (음수를 제외한 0과 양수) - 음수가 없는만큼 2배의 크기를 제공
    - **8~64비트 특정 데이터 크기보다는 기본형을 사용하길 권장**
    - Int 데이터 타입은 코드 실행 플랫폼에 맞는 정수 크기를 사용함
  - 실수(Floating-point Number)형 데이터(32,64비트 지원)
    - Float(실수타입, 부동소수타입) - 32비트
      - 정수포함 6자리까지 표현가능, 4byte
    - Double(실수타입, **Float에 비해 2배의공간**) - 64비트
      - 정수포함 15자리까지 표현가능, 8byte
      - **Swift에서** **주로사용**
  - 문자형 데이터 타입
    - Character 문자
      - 하나의 문자(한 글자)
    - String 문자열
      - 문자열을 저장
      - **Swift에서 주로사용**
    - 문자/문자열은 반드시 쌍 따옴표( “ ” )안에 써야 한다
    - 여러 줄의 문자열은 삼중 따옴표( “ ” ” ) 을 사용한다 
  - 참,거짓(Boolean)데이터 타입: `true` / `false`
- 특수 문자
  - 문자열 내에서 일정한 기능을 하는 문자( 제어 문자라고 도 한다)
  - \\ + 특정문자를 조합해서 사용한다
  - (\n - 줄바꿈),  \(\\ - 문자열 내에서 백슬래시 사용),  (\” - 큰 따옴표를 사용),  (\t - 탭 문자, 탭키를 누른것과 같은 효과), (\0 - 문자열이 끝났음을 알리는 null문자) 등등 
---
- 변수(Variable)
  - 데이터(자료)를 담을 수 있는 공간
  - **데이터 값은 변할 수 있다.**
  - 이름: 식별자 / 한 영역에 유일한 하나의 이름만 사용 해야함
  - `var` 키워드 사용 ( var [변수명] : [데이터타입] = [값] 형태로 선언)
  - 데이터 타입은 생략 가능
- 상수(Constant)
  - 데이터(자료)를 담을 수 있는 공간
  - **데이터 값은 변할 수 없다**
  - 이름: 식별자 / 한 영역에 유일한 하나의 이름만 사용 해야함
  - `let` 키워드 사용 ( let [상수명]: [데이터 타입] = [값]의 형태로 선언)
  - 항상 같은 값(변하지 않는 값)  -> 값이 변경하면 오류발생
  - ---
- 타입 추론(Type inference)
  - `var num: = 4`   와 같이  데이터형을 명시 하지 않았을때  데이터형을 Int형으로 추론해서 지정
  - `var num: = 4.0` 같은 경우 Float형이 아닌 Dobule형으로 추론된다.
- 타입 어노테이션(Type annotation)
  - `var num: Int = 4`와 같이 데이터형을 직접 명시
- 타입 추론은 타입 어노테이션에 비해 타입을 추론하는 과정으로 인해 컴파일러 시간이 오래 걸린다.
- 상수는 타입 추론을 사용하기 위해서는 초기 값을 지정해줘야 한다.
---
- 튜플(Tuple)
  - 원하는 여러가지의 데이터 조합으로 만들 수 있는 타입
  - 선언과 동시 데이터의 자료형 및 멤버의 개수는 추가/삭제 불가
  - 하나의 함수에서 여러 값을 반환할 수 있다
  - Named Tuple
    - `(tuplename1: num1, tuplename2: num2)`와 같이  멤버 앞에 붙여준다.
    - 접근 할 때 index(숫자)가 아닌  이름으로 접근 가능
  - 튜플 분해(Tuple Decomposition)
    ``` 
    var people = (name: "seonggeun", age: 28, address: "seoul")
    
    let name = people.name
    let age = people.age
    let address = people.address
    
    튜플의 멤버를 각각의 상수에 저장가능
- ---
- 옵셔널 타입(Optional)
  - nil 값이 없음을 표현하는 키워드
  - 값이 할당되거나 아무런 값도 할당되지 않을 수 있다.(`nil`)
  - 변수를 선언할때 타입 뒤에 `?`를 사용한다
  - 값이 할당되지 않았을때 오류를 해결하기 위해 만들어졌다.
  - 옵셔널(Optional)타입 추출 
    - 강제 추출(Forced Unwrapping) -  nil이 아닌 값이 있다는 것을 확신하고 강제로 값을 추출
      - 사용 예시 -  `num!`
    - 닐(nil) 코얼레싱(병합) - nil 값이 들어오면 기본값을 지정해준다
      - 사용 예시 - `optionalNum ?? 0`
    - 옵셔널 바인딩(if let / guard let) - 값을 안전하게 확인하고 옵셔널을 추출한다
      - 사용예시 -
``` if let 바인딩
if let num = optionalNum {
			print(num)
}
	guard let 바인딩
guard let num = optionalNum else { return
   
}
```
			
---
- 타입 캐스팅(Type Casting)과 타입 검사
  - 인스턴스의  “타입” 을 확인하거나 해당 인스턴스를 슈퍼클래스나 하위 클래스로 취급하는 방법
  - `is` 혹은 `as` 연산자로 구현된다
  - is 연산자
    - ``표현식 is Type``  으로 사용
    - 타입을 체크하는 연산자로 런타임 시점 실제 체크가 이루어진다.
    - 반환 값은 `Bool`형이다
  * as 연산자
    * ```표현식 as (변환 할)Type
      	표현식 as? (변환 할)Type
      	표현식 as! (변환 할)Type
      ```
    - 표현식이 변환할 타입과 호환된다면 변환할 타입으로 캐스팅된 인스턴스를 반환한다.
    - 업캐스팅(Upcasting): 서브 클래스의 인스턴스를 슈퍼 클래스의 타입으로 참조
      - as 연사자를 사용한다
      - 업캐스팅은 항상 성공한다.
      - 컴파일 시점에 캐스팅 가능 여부를 결정한다
    - 다운캐스팅(Downcasting): 슈퍼 클래스의 인스턴스를 서브클래스의 타입으로 참조
      - 업캐스팅된 인스턴스를 다시 원래 서브 클래스 타입으로 참조할 때 사용한다
      - as?, as! 연산자를 사용한다
        - as? : 런타임 시점에 다운 캐스팅을 하며 실패할 경우 nil을 리턴한다
        - as! : 런타임 시점에 다운 캐스팅을 하며 실패할 경우 에러를 발생
      
    
