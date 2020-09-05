# 정규표현식. 정규식 (Regular Expression)
-  정규표현식
   -  문자열 매칭 기능, 교체 기능 제공
   -  문자열 속에서 부분 문자열을 찾는 일 + 찾은 부분 교체

- 정규식 만들기
  ```javascript
   // 1. 정규표현식 리터럴. 슬래시로 감싼 형태
  const re1 = /going/;

  // 2.RegExp 생성자 사용
  const re2 new RegExp("going"); 
  ```

- 정규식 검색
```js
const input = "As I war going to Saint Ives";
// 세 글자 이상인 단어
const re = /\w{3,}/ig;

// 문자열 메서드 사용
input.match(re); // ["was", "going", "Saint", "Ives"]
input.search(re); // 5 (인덱스)

// 정규식 메서드 사용
re.exec(input) // ["was"]
```

- 자주 쓰는 메서드
  - [RegExp.prototype.exec](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec)
    - 결과를 배열 혹은 null 로 반환
  - [RegExp.prototype.test](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test)
    - true / false 반환
  - [String.prototype.match](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/match)
    - 결과를 배열 혹은 null 로 반환
  - [String.prototype.search](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/search)
    - 매칭된 문자열의 인덱스 리턴 / -1 리턴
  - [String.prototype.replace](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
    - 패턴에 일치하는 부분이 교체된 새로운 문자열

- i : Ignore Case.대소문자 가리지 않고 
- g: Global. 전체 검색 (없으면 첫번째 항목만 반환)
- | : 대체 , or의 의미
- m: Multi Line.
- 자주 쓰는 문자 셋
  - \d  (= [0-9]) : 숫자
  - \D (= [^0-9] ): 숫자가 아닌것
  - \s (= [ \t\v\n\r]) : 탭, 스페이스, 세로 탭, 줄바꿈 포함한 여러 공백 문자
  - \S (= [^ \t\v\n\r])  공백이 아닌 모든 문자.
  - \w (= [a-zA-Z_])
  - \W (= [^a-zA-Z_])
- 반복 메타 문자
  - {n} : n개
  - {n,} : 최소 n개 
  - ? : 0개 또는 1개
  - \* :  0회 이상  ( ={0,})
  - \+ 하나 이상
  - . 임의의 문자 1개. 줄바꿈 문자 제외하는 모든 문자.
- 그 외
  - ^: 문자열의 처음
  - $ :문자열의 끝
  - \[^]: 부정