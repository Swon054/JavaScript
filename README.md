# TIL-JavaScript
Today I learn

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
