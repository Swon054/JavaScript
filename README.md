# TIL-JavaScript
모던 자바스크립트에 대해 배운 것 

## 2022-09-28
### Day1
#### `script` 태그
- 대부분 html 위치에 script태그를 사용할 수 있다. 
- 자바 스크립트 프로그램 삽입 용도로 사용한다.
```
<!DOCTYPE HTML>
<html>

<body>

  <script>

    alert('hello world')

  </script>

</body>

</html>
```
* `alert`는 `print` 용도로 사용한다.

#### 모던 마크업

- `script` 태그에서는 사용할 수 있는 속성이 몇 가지 있음
1. `type` 속성 : <script type = ...>
- HTML4에서는 vb와 같은 script가 기본인 브라우저가 있었지만, HTML5에서는 JavaScript가 기본이기 때문에 
속성의 의미가 달라졌다.
2. `language` 속성 : <script language = ...>
- 스크립트 언어를 나타내는 속성
- 현재는 JavaScript가 기본 언어이기 때문에 사용할 필요는 없다
*예시
```
<script type = "text/javascript"><!-- 주석>
//--><script>
```

## 2022-09-29
### Day2
#### 외부 스크립트
```
<script src = "filePath.js"></script>
```
- 스크립트의 양이 많을 경우 소분화하여 외부 스크립트를 불러오는 식으로 사용한다
- HTML 내 스크립트를 사용하는 경우는 간단한 코드일 경우이다
- 여러 스크립트를 삽입하는 경우 다음과 같이 여러 번 코드를 입력한다
```
<script src = "filePath1.js"></script>
<script src = "filePath2.js"></script>
...
```
  
#### 코드 구조

##### 문(Statement)
- 명령어와 문법 구조의 단위
- 각 Statement는 가독성을 위해 서로 다른 줄에 쓴다
  
##### 세미콜론(semicolon)
- 각 Statement의 끝을 의미함
- 줄바꿈 시 `세미콜론 자동 삽입(automatic semicolon insertion)`이 발생한다.
* 세미콜론 자동 삽입은 불완전한 표현식에는 작동하지 않는다.
  
##### 주석(comment)
- 개발자가 작성한 코드의 의도를 보여주기 위한 것
- `//`는 한 줄 주석, `/*...*/`은 여러 줄 주석
- 항상 주석을 다는 습관을 들이는 것이 중요함

## 2022-09-30
### Day3
#### use strict
- 스크립트 전체를 모던화 시켜주는 명령어
- 최상단에 위치시키면 코드 전체를 use strict모드로 활성화시켜준다
```
"use strict"
```
`use strict`를 활성화하면 취소시키는 방법은 없다
##### 브라우즈 콘솔을 사용하는 경우
- 엄격 모드 활성화 : `use strict`를 친 후, `Shift` + `Enter`을 눌러주고 코드를 작성하면 활성화 된다.
* `use strict`는 클래스와 모듈을 사용한다면 생략가능

#### 변수와 상수  
##### 변수
- JavaScript에서는 변수를 `let`함수를 이용해서 선언한다.
```
  let x;
  x = 6; // x에 6 데이터 할당해라
  
  alert(x); // x를 출력해라
```
- 한 줄에 `let`과 데이터 할당 가능
```
  let x = 6;
  alert(x)
  ```
* 가독성을 위해서 한 줄에는 변수 하나씩 선언하기

##### 변수 명명 규칙
- 카멜 표기법(camelCase)을 흔히 사용한다. ex) myName, itemPrice, ...
- 변수명에 `$`와 `_`도 사용 가능하다
- 예약어(let, reture, class 등..)은 JavaScript에서 사용하고 있기 때문에 변수명으로 사용할 수 없다
  * 참고 : `use strict`를 사용하지 않는 경우, `let`함수를 사용하지 않고 구버전 스크립트와 호환이 가능하다
  1. 변수를 명명할 때는 항상 유지보수를 고려해서 명명한다 
  2. 규칙을 따르거나 정하면 좋다 
  3. 너무 간결한 변수명은 혼란을 일으킬 수 있다
  
##### 상수
- 변하지 않는 수를 할당할 때는 `let`대신  `const`를 사용
```
  const pi = 3.14159265359 // pi의 값
```
- 상수는 변수와 다른 대문자와 `_`를 이용해서 명명

## 2022-10-02
### Day3
#### 자료형
- JavaScript에는 8가지 기본 자료형이 있다
- 데이터의 타입에 맞게 자료형을 설정해줘야 한다

##### 숫자형
- 정수와 부동소수점 숫자를 나타낸다
- 숫자형과 관련된 연산자 : `*`, `/`, `+`, `-`, `%`
- 특수 숫자 값 : `Infinity`, -`-Infinity`, `NaN`
  
* BigInt
- 숫자형과 달리 길이와 상관없이 정수를 표현할 수 있게 하는 자료형
- 숫자 뒤에 `n`을 붙여서 만들 수 있다.
*참고 : Firefox, Chrome, Edge, Safari같은 브라우저에서는 지원하나, IE에서는 지원하지 않음 (2022-08-13기준)
  
##### 문자형
- 따옴표(")로 문자형으로 나타내고자 하는 데이터를 묶어주면 문자열로 표현할 수 있다
```
let name = "Sangwon";// name에 Sangwon이라는 변수 저장
alert(name); // Sangwon
```
- `${...}`을 이용해 다음과 같이 조합도 가능하다
- 이 경우 숫자도 조합가능하다!
```
  alert("My name is,${name}"); // My name is Sangwon
  alert("1+2 =, ${1+2}"); // 1+2의 값 출력
```
  
##### 불린형
- `true`와 `false`, 두 가지 값만 있는 자료형
```
let fieldChecked1 = true; // fieldChecked1에 true값 할당
let fieldChecked2 = false; // fieldChecked2에 false값 할당
```
- 비교 결과 저장도 가능하다
- 논리 연산자에서 많이 쓰인다
  
##### 'null'
-  `null`을 어느 자료형에도 속하지 않는 값
- JavaScript의 `null`은 존재하지 않는 다는 의미로 쓰인다


##### 'undefined'
- 값이 할당되지 않은 상태를 나타낸다
- 다음과 같은 경우 `undefined`가 할당된다
```
let age;

alert(age); // 'undefined'가 출력
```
- 개발자가 명시적으로 할당할 수 있다, but `null`값을 사용하는 것이 권장됨

#### 객체와 심볼
- `object`형 : 데이터 컬렉션이나 복잡한 개체(entity)를 표현할 수 있다
- `symbol`형 : 객체의 고유한 식별자를 만들 때 사용한다

##### typeof 연산자
- 연산자와 함수를 표현하는 문법이 다름
1. 연산자 : typeof x
2. 함수 : typeof(x)
- 사용 예시는 다음과 같다
```
typeof undefined // "undefined"

typeof 2 // "number"

typeof 1013231312213n // "bigint"

typeof true // "boolean"

typeof "April" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```

## 2022-10-03
### Day4
####  alert, prompt, confirm
##### alert
- 개발자가 할당한 변수 데이터를 보여주는 모달 창(Modal Window)을 보여준다
- 해당 브라우저 탭은 `확인`버튼을 누르기 전까지는 아무 동작을 할 수 없다
```
alert("hello"); // "hello"를 출력
```

##### prompt
- `prompt`는 두 개의 인수를 받는다
```
test = prompt(title, [default]);
```
1. title : 사용자에게 보여주는 메시지
2. default : default로 설정할 값(여기서 `[...]`는 절대값이 아닌 선택값을 의미함)

##### confirm
- 개발자가 입력한 메시지와 `예` 또는 `아니요`버튼을 포함한 모달 창을 보여준다
```
test = confirm(question); // 이지선다형 질문 모달 창을 출력
```
- `예`는 `true`, `아니오`는 `false`값으로 반환된다

## 2022-10-04
### Day5
#### 형 변환
- 자료형의 `type`을 변경하는 것이다.

##### 문자형으로 변환
- 문자형의 값이 변환되어야 할 때 사용한다
- alert메서드는 매개변수를 자동으로 문자형으로 변환시킨다
- `String(value)`함수를 호출해서 개발자가 인위적으로 변환가능
```
let value = true; // value에 true를 할당
value = String(value); // 변수 value를 boolean에서 String으로 변환
alert(typeof value); // value의 변수 타입 출력
```

##### 숫자형으로 변환
- boolean 및 문자형에서 숫자형으로의 변환은 수학 관련 함수와 표현식에서 자동으로 변환된다
- `Number(value)`함수를 호출해서 개발자가 인위적으로 변환가능
```
let str = "123"; // 변수 str에 문자형 123을 할당
alert(typeof str); // str의 타입 출력

let num = Number(str); // str을 숫자형으로 변환
alert(typeof num); // 형 변환된 num의 타입을 출력
```

##### 불린형으로 변환
- 불린형은 `true`와 `false`로 변환된다
- '비어있는' 느낌의 값(`0`, `null`, `undefined`, `NaN`)은 `false`가 된다
- 그 외의 값은 `true`로 변환된다.
```
alert(Boolean(1)); // 숫자 1을 불린형으로 변환
alert(Boolean(0)); // 숫자 0을 불린형으로 변환

alert(Boolean("This is String:)); //문자열을 불린형으로 변환
alert(Boolean("")); //빈 문자열을 불린형으로 변환
```
