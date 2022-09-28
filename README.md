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
