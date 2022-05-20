# Javascript Study 
> Vanilla JS 개념 공부

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=JavaScript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=Node.js&logoColor=white)
![npm](https://img.shields.io/badge/npm-CB3837?style=flat-square&logo=npm&logoColor=white)


## :bulb: Javascript 란?

```sh
* 자바스크립트는 "웹페이지에 생동감을 불어넣기 위해" 만들어진 프로그래밍 언어
* 자바스크립트는 자체적으로 실행되지 않으며, 실행하려면 자바스크립트 엔진이 필요 (Chrome : V8, Firefox : SpiderMonkey )
* Vanilla JS : 핵심이 되는 아무것도 포함되지 않은 순수 자바스크립트를 함축적으로 표현하는 것
```

## :question: Javascript 는 인터프리터 언어?　컴파일러 언어?
```sh
* 인터프리터 언어 : 고급 언어(사람이 이해하고 작성하기 쉬운 코드)로 작성된 프로그램을 한 줄 단위로 받아들여 번역하고, 번역과 동시에 프로그램을 한 줄 단위로 즉시 실행하는 언어
* 컴파일 언어 : 프로그래밍된 코드를 실행할 때 모든 코드를 컴파일러를 통해 기계어로 변환한 후에 파일을 생성하여 그 파일을 실행하는 언어

- 결론 : 자바스크립트는 "HTML 페이지를 동적으로 만드는 것"에 목적이 있어 가벼운 인터프리터 언어로 만들어졌다. 하지만, 자바스크립트의 성능을 크게 향상 시키기 위하여 실행되는 플랫폼에 따라 엔진(대부분의 현대 자바스크립트 엔진) 내부에서 컴파일 과정을 거친다.
```

## :eyes: Javascript 변수 선언자 (var, let, const)
```sh
* 변수(variable)는 하나의 값을 저장하기 위해 확보한 메모리 공간 자체 또는 그 메모리 공간을 식별하기 위해 붙인 이름
* 자바스크립트 변수 선언은 "선언" -> "초기화" 단계를 거쳐 수행된다.
  -> 선언 단계 : 변수명을 등록하여 자바스크립트 엔진에게 변수의 존재를 알린다.
  -> 초기화 단계 : 값을 저장하기 위한 메모리 공간 확보 및 "undefined" 를 할당해 초기화 한다.
* 호이스팅(hoisting) : 변수 선언이 어디에 있든 상관없이 다른 코드보다 먼저 실행되는 특징
  -> 자바스크립트 엔진은 소스코드를 한 줄씩 순차적으로 실행하기에 앞서, 변수 선언을 포함한 모든 선언문(ex. 변수 선언문, 함수 선언문 등)을 찾아내 먼저 실행한다.
```
* var 
    * ES6 이전 변수를 선언할 수 있는 키워드
    * 해당 키워드로 변수 선언 시 선언 단계와 초기화 단계가 동시에 진행된다.
    * 해당 키워드의 문제점
      * 변수 중복 선언 가능하여, 예기치 못한 값을 반환할 수 있다.
      * 함수 레벨 스코프로 인해 함수 외부에서 선언한 변수는 모두 전역 변수로 된다.
      * 변수 선언문 이전에 변수를 참조하면 언제나 "undefined" 를 반환한다.
* let
    * ES6 이후 변수를 선언할 수 있는 키워드
    * 변수의 중복선언 불가, 재할당 가능
* const
    * ES6 이후 변수를 선언할 수 있는 키워드
    * 변수의 중복선언, 재할당 불가 (반드시 선언과 초기화를 동시에 진행해야 한다.)
    * 변경하지 않는 값(상수)로 사용

## :eyes: Javascript 변수 타입
### 원시타입 (Primitive Type)
```sh
  * 메모리의 고정 크기로 원시 값을 저장하고 해당 저장된 값을 변수가 직접적으로 가리키는 형태 
  * 불변성(Immutability) : 재할당 시 기존 값이 변하는것 처럼 보일지 몰라도 사실 새로운 메모리에 재할당한 값이 저장되고 변수가 가리키는 메모리가 달라짐
  * Pass By Value(값에 의한 전달) : 복사된 데이터를 전달하여 구성함으로써, 값을 수정하여도 원본의 데이터에는 영향을 주지 않도록 하는 방식
  * 종류 : String, Boolean, Null, Undefined, Number, Bigint, Symbol
  
  예시1)
  let a = 100;
  a = 50;
  console.log(a) -> 50
  
  예시2)
  let a = 100;
  let b = a;
  a = 50;
  console.log(a) -> 50
  console.log(b) -> 100
  
  * 참고 사이트 : https://velog.io/@nomadhash/Java-Script-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC%EC%99%80-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC
```
![primitive1](https://velog.velcdn.com/images%2Fnomadhash%2Fpost%2F5e197937-108e-4f9c-8be8-0c8c04d3fe8e%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-09-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%207.02.57.png)
![primitive2](https://velog.velcdn.com/images%2Fnomadhash%2Fpost%2F4c48d687-2e50-42d0-a72a-28058f114cd1%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-09-18%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.01.34.png)
* Number(숫자) : 64비트 부동소수점 형식으로, 모든 숫자를 실수로 처리하고 연산도 가능
    * let num1 = 7;
    * let num2 = 3.14;
* String(문자열) : 16비트 유니코드 문자셋(UTF-16) 형식으로, 홑따옴표(' ') / 쌍따옴표(" ") 로 문자열 할당 가능
    * let firstName = 'Beau';
    * let lastName = 'Kim';
* Boolean(논리형) : 논리적 참, 거짓을 나타내는 true, false 로 표현
    * let isMale = true;
    * let isFemale = false;
* Null : 의도적으로 "값이 없음"을 명시하기 위해 할당
    * let n = null;
    * null 은 객체가 아닌 기본타입이며, typeof 연산자로 체크하는 경우 object 라고 표기되는건 자바스크립트 버그
* Undefined : 어떤 변수를 선언하고 값이 할당되지 않았을때 자바스크립트 엔진에서 암묵적으로 초기화 하는 값
  * let u1;
  * let u2 = undefined;
  * "undefined"는 단어의 의미 그대로 정의되지 않음이라는 뜻이며 값이 대입되지 않은 상태를 위해 많이 사용되며, "null"이라는 값은 의도적으로 값이 없음을 표현하고 싶을 때 사용
* Symbol : 이름의 충돌 위험이 없는 유일한 객체의 Property Key 를 만들기 위해 사용
  * const sym = Symbol('name');
* Bigint : 길이의 제약 없이 정수를 다룰 수 있게 해주는 숫자형
  * const bigNum = 1234567890123456789012345678901234567890n;

### 참조타입 (Reference Type)
```sh
* 메모리에 직접 접근이 아닌 메모리의 위치(주소)에 대한 간접적인 참조를 통해 메모리에 접근하는 데이터 타입
* Pass By Reference(참조에 의한 전달) : 주소 값을 전달하여 실제 값에 대한 Alias를 구성함으로써, 값을 수정하면 원본의 데이터가 수정되도록 하는 방식
* 종류 : Object, Array, Function, Regular Expressions

  예시1)
  let myArr = [];
  let copyArr = myArr;
  myArr.push("hello");
  console.log(copyArr); -> ["hello"]
  
  * 참고 사이트 : https://velog.io/@nomadhash/Java-Script-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC%EC%99%80-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC
```
![reference1](https://velog.velcdn.com/images%2Fnomadhash%2Fpost%2Fac894f26-b94a-41f8-990e-8b44c6775d97%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-09-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%207.54.37.png)
* Object : 객체
  * let person1 = {};
  * let person2 = {firstName : "Beau", lastName : "Kim", age : 29};
* Array : 배
  * let arr1 = ["KIA", "BMW", "Volvo"];
  * let arr2 = [9, 4, 0, 11, 7];