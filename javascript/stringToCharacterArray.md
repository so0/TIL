# String 을 Character Array로 `변경하기

-  `"Hello world!"` => 
    `["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!"]`

    1. String split() Method
        - 'Hello World!'.split('');

    2. Spread syntax 
        - [...'Hello World']

    3. Array.from() method
        - Array.from('Hello World!')

    4. Object.assign() method
        - Object.assign([], 'Hello World!')
   
- Charactor Array => String (원복)
    1. Array join Method
        -  ["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!"].join('');