## Array Method - filter, map, reduce(/redueRight)
 - 자바스크립트 내장 배열 메소드.
 - function 을 인자로 받는다.
 - 원본을 변경하지 않고 새로운 배열 or 결과값 리턴
### 1. filter
 - arr.filter(callback(element[, index[, array]])[, thisArg])
 - filter() 메서드는 주어진 판별 함수를 통과하는 요소를 모아 **새로운 배열**로 만들어 반환합니다.
 
 - callback 함수 (`element`, `index`, `array`) 
    - `element` 현재 처리할 요소
    - `index` 현재 인덱스
    - `array` 원본 배열
 - thisArg
    - callback을 실행할 때 this로 사용할 값
 ```javascript
 const arr = [1, 2, 3, 4, 5];
 const res = arr.filter(function() {
     return item %2 === 0; // 조건
 })
 console.log(res); // [2, 4]
 ```

### 2. map
 - arr.map(callback(element[, index[, array]])[, thisArg])
 - map() 메서드는 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 **새로운 배열**을 반환합니다.
 - 값이 삭제되거나 아직 값이 할당/정의되지 않은 인덱스(`undefined`)에 대해서는 호출되지 않습니다.
 - map을 호출한 배열의 중간이 비어있는 경우, 결과 배열 또한 동일한 인덱스를 빈 값으로 유지합니다.
 
 - callback 함수 (`element`, `index`, `array`) 
 ```javascript
 const arr = [1, 2, 3, 4, 5];
 const res = arr.map(function(item) {
     return item * 2; 
 })
 console.log(res); // [2, 4, 6, 8, 10]
 ```

### 3. reduce 
 - arr.reduce(callback[, initialValue])
 - 배열의 각 요소에 대해 주어진 리듀서(reducer) 함수를 실행하고, 하나의 결과값을 반환합니다. 
 - 빈 요소를 제외하고 배열의 0번부터 실행됨.
 - initialValue 가 없으면 첫 번째 요소가 initialValue가 됨.
 - Callback Parameter 
    - callback(accumulator[, currentValue[, currentIndex[, array]]])
    - **`accumulator`** (acc) : 콜백의 반환값을 누적함.
    - `currentValue` (cur) 현재 값
    - `currentIndex` (idx) 현재 인덱스
    - `array` (src) 원본 배열
 - 리듀서 함수의 반환 값은 누산기에 할당되고, 누산기는 순회 중 유지되므로 결국 하나의 값이 된다.
 ```javascript
 const arr = [1, 2, 3, 4, 5];
 const res = arr.reduce(function(acc, cur) {
     return acc + cur;
 }, 0);
 
 // acc + cur 
 // 0 + 1 = 1
 // 1 + 2 = 3
 // 3 + 3 = 6
 // 6 + 4  = 10
 // 10 + 5 = 15
 console.log(res); // 15

 [0, 1, 2, 3, 4].reduce( (prev, curr) => prev + curr );
 ```

### 4. reduceRight
- arr.reduceRight(callback[, initialValue])
- reduceRight() 메서드는 누적기에 대해 함수를 적용하고 배열의 각 값 (오른쪽에서 왼쪽으로)은 값을 단일 값으로 줄여야합니다.

``` javascript
var flattened = [[0, 1], [2, 3], [4, 5]].reduceRight(function(a, b) {
    return a.concat(b);
}, []);
// flattened is [4, 5, 2, 3, 0, 1]
```