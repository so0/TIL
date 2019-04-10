# Map과 Set
 - ES6에서 새로 도입한 데이터 구조.
 - 맵은 키와 값을 연결하는 객체와 비슷하고, 셋은 중복을 허용하지 않는 것을 제외하면 배열과 비슷하다.

### Map
- 객체의 단점
    - 프로토타입 체인으로 의도하지 않은 연결이 생길 수 있다.
    - 객체 내에 연결된 키, 값이 몇 개인지 알 수 없다.
    - 키는 문자열이나 심볼이어야 한다.
    - 객체를 키로써 사용 불가능하다.
    - 객체는 프로퍼티 순서를 보장하지 않는다.
- Map 특징
    - `Key` - `Value` 쌍으로 저장된다.
    - 각 쌍의 순서를 기억한다.
    - 아무 값이나 키/값으로 사용 가능하다.
    - Map객체는 간단한 키와 값을 서로 연결(매핑)시켜 저장하며 저정된 순서대로 각 요소들을 반복적으로 접근할 수 있도록 한다. 

``` javascript
const u1 = {name: 'Cynthia'};
const u2 = {name: 'Jakson'};
const u3 = {name: 'Olive'};
const u4 = {name: 'James'};

const userRoles = new Map();

// set 메서드
userRoles.set(u1, 'User');
userRoles.set(u2, 'User');
userRoles.set(u3, 'Admin');

// set 메서드를  체인으로 연결 가능
userRoles
    .set(u1, 'User')
    .set(u2, 'User')
    .set(u3, 'Admin');

// 생성자에 배열의 배열을 넘기는 형태
const userRoles = new Map([
    // [key, value],
    [u1, 'User'],
    [u2, 'User'],
    [u3, 'Admin'],
]);

// get 메서드
userRoles.get(u2) //'User'
userRoles.get(u4) // undefined
userRoles.has(u1) // true
userRoles.has(u4) // false

// 이미 존재하는 키에 set호출 시 값이 교체됨
userRoles.get(u1) //'User'
userRoles.set(u1, 'Admin');
userRoles.get(u1) //'Admin'


// size 프로퍼티로 맵 내부 요소의 갯수 확인 가능
userRoles.size // 3

// 맵의 요소 삭제
userRoles.delete(u1);

// 전체 요소 삭제
userRoles.clear();
userRoles.size;     // 0
```

- keys(), values(), entries() 메서드
    - 각 메서드는 이터러블 객체 반환
    - `keys()` : 맵의 key로 이루어진 이터러블 객체 반환
    - `values()` : 맵의 value로 이루어진 이터러블 객체 반환
    - `entries()` : 맵의 각 항목. [key, value] 쌍으로 이루어진 이터러블 객체 반환

``` js

for(let u of userRoles.keys()) 
    console.log(u.name);

for(let r of userRoles.values()) 
    console.log(r);

for(let ur of userRoles.entries()) 
    console.log(`${ur[0].name}: ${ur[1]}`);

// destruct
for(let [u, r] of userRoles.entries()) 
    console.log(`${u.name}: ${r}`);

// entries() 메서드는 맵의 기본 이터레이터. .entries() 단축하여 사용 가능
for(let [u, r] of userRoles)  
    console.log(`${u.name}: ${r}`);

```

- Map과 Object 선택 팁
    - 실행 시까지 키를 알수 없고, 모든 키가 동일한 type이며 모든 값들이 동일한 type일 경우 => **map**
    - 각 개별 요소에 대해 적용해야 하는 로직이 있을 경우 =>  **objects** 

### Set
 - Set객체는 값들의 집합이다.
 - 입력된 순서에따라 저장된 요소를 반복처리할 수 있다.  (순서 보장)
 - Set은 중복된 값을 허용하지 않는다. (배열과 다른 점)
 - 중복을 허용하지 않는 데이터 집합.

- 배열 단점 및 Set 장점
    - indexOf메서드를 사용하여 배열 내에 특정 요소가 존재하는지 확인하는 것은 느리다.
    - 배열에선 해당 요소를 배열에서 잘라내야 하는 반면 Set객체는 요소의 값으로 해당 요소를 삭제하는 기능 제공한다.
    - NaN은 배열에서 indexOf메서드로 찾을 수 없다. 
    - Set객체는 값의 유일성을 보장하기 때문에 직접 요소의 중복성을 확인할 필요가 없다. 

 ``` js
const roles = new Set();

roles.add('User');  // Set ["User"]
roles.add('Admin'); // Set ["User", "Admin"]

roles.size; // 2

roles.has("User"); // true

// 제거 성공 시 true, 실패 시 false 반환
roles.delete('Admin');   // true
roles;                  // Set ["User"]
roles.delee('Admin');   // false
 ```


- Set 과 배열
    - Array.from 혹은 spread operator를 통해 Set객체를 가지고 Array을 생성할 수 있다.
    - Set 생성자는 배열을 인자로 받을 수 있다.
    - 단  Set객체는 중복된 값을 저장하지 않기 때문에 주어진 배열 내의 중복된 요소들을 제거되어 Set으로 변환된다. 
``` js
var mySet = new Set();
mySet.add(1);
mySet.add("some text");
mySet.add("foo");

Array.from(mySet);
[...mySet2];

mySet2 = new Set([1,2,3,4]);
```