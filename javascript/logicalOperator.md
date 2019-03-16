# 논리 연산자
- 자바스크립트의 논리 연산자
    - AND(&&), OR(||), NOT(!)
- 논리 연산자는 보통 Boolean(논리적) 값과 함께 쓰이며, 불리언 값을 반환. (대부분의 프로그래밍 언어)
- 자바스크립트의 논리 연산자는 **불리언이 아닌 값**도 다룰 수 있고 (피연산자로 불리언이 아닌 값 사용 가능), **불리언이 아닌 값을 반환**하기도 한다. (논리 연산 결과가 불리언이 아닐 수 있다.)
- `&&`과 `||` 연산자는 **피연산자 중 하나의 값**을 반환한다.
    - 불리언 외의 다른 값과 함께 사용하면 불리언 값이 아닌 것을 반환할 수 있습니다.

 - 자바스크립트에서는 모든 데이터를 참, 거짓으로 변환할 수 있다.
    - 거짓으로 변환할 수 있는 값 (거짓 같은 값)
        1. null
        2. NaN
        3. 빈 문자열 ("", '', ``)
        4. undefined
        5. 0
        6. false

    - 참으로 변환할 수 있는 값 (참 같은 값)
        1. 모든 객체 (빈 객체더라도 항상 참으로 변환)
        2. 배열 (빈 배열)
        3. 공백만 있는 문자열 (" ")
        4. 문자열 "false" 
        

 - 피연산자가 불리언이 아닐 때 논리연산자가 동작하는 방법.
    - 피연산자가 불리언이 아니면 **결과를 결정한 값**이 반환된다. (불리언이 아니라)
    ``` javascript

    const option = suppliedOptions || {name: "Default"};

    //suppliesOptions 가 undefined, null 이면 (왼쪽 피연산자가 false일 때) option 은 {name: "Default"}

    //suppliesOptions 객체가 존재하면 (왼쪽 피연산자가 true 이면) option은 suppliesOptions

    
    // Logical AND (&&)
    a5 = 'Cat' && 'Dog'      // t && t returns "Dog"
    a6 = false && 'Cat'      // f && t returns false
    a7 = 'Cat' && false      // t && f returns false
    a8 = ''    && false      // f && f returns ""
    a9 = false && ''         // f && f returns false

    // Logical OR (||)
    o5 = 'Cat' || 'Dog'      // t || t returns "Cat"
    o6 = false || 'Cat'      // f || t returns "Cat"
    
    o7 = 'Cat' || false      // t || f returns "Cat"
    o8 = ''    || false      // f || f returns false
    o9 = false || ''         // f || f returns ""

    // 예시코드
    function documentTitle(theTitle)
    theTitle  = theTitle || "Untitled Document";
    }

    documentTitle("title") // theTitle = "title"
    documentTitle()        // theTitle = "Untitled Document";
    ``` 


- 단축 평가 (Short-circuit evaluation) , 단락 평가
    - 두 값을 모두 평가하지 않아도 될 때가 있음.
        - `x && y`에서 `x` 가 거짓이면는 `y`를 평가할 필요도 없이 `false`.
        - `x || y` 에서 `x가` 참이면 `y`를 평가할 필요도 없이 `true`.
    - 논리 표현식을 좌측부터 평가하므로, 아래 규칙에 따라 단락(short-circuit) 평가를 수행합니다.
      - `(거짓 표현식) && expr`은 거짓 표현식으로 단락 평가됨
      - `(참 표현식) || expr`은 참 표현식으로 단락 평가됨
      - 첫 번째 피연산자를 평가한 순간 이미 연산자의 결과가 정해지기 때문.