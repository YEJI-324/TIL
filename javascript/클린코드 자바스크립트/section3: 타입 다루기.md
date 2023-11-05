# 섹션3: 타입 다루기

# 10. 타입 검사

js에서 타입 검사를 할 때 ‘typeof’ 연산자를 사용.

타입을 문자열로 **반환** → ‘string’, ‘boolean’, ‘undefined’, ‘number’, ‘symbol’

```jsx
typeof '문자열'
typeof true
typeof undefined
typeof 123
typeof Symbol()
```

### PRIMITIVE vs REFERENCE 자료형

- primitive: 원시값, 불변
- reference: object → Array, Function, Date…
⇒ `typeof`로 분별하기 어려움

```jsx
function myFunction() {}
class MyClass {}

typeof myFunction // -> 'function'
typeof MyClass // -> 'function'

// wrapper 객체
const str = new String('문자열')
typeof str // -> 'object'
```

reference 값은 typeof로 판별하기 어렵다.

+ js가 동적으로 변하는 언어 ⇒ 타입도 동적으로 변함.

### null

```jsx
typeof null // -> 'oeject'
```

js의 언어적인 오류..

### instanceof

객체 프로토타입 체인을 검사하는 연산자

```jsx
function Person(name, age) {
	this.name = name;
	this.age = age;
}

const p = {
	name: 'yeji',
	age: 24
}

const yeji = new Person('yeji', 24);

yeji instanceof Person // -> true
p instanceof Person // -> false
```

instanceof 로 Array, Fuction, Date 등 검사할 수 있음. 하지만 상위 프로토타입이 oeject이므로  `~~ instanceof Object`도 true를 리턴함.
⇒ Object 의 프로토타입을 역으로 이용함.

```jsx
Object.prototype.toString.call('') // -> '[object String']
Object.prototype.toString.call(new Date()) // -> '[object Date']
```

wrapper 객체까지 감지를 해줌.

# 11. undefined & null

값이 없거나 정의되지 않은 것!

null: 비어있는 값을 명시적으로 표현하지만, 수학적으로는 0.. typeof는 ‘Object’

undefined: 변수 선언 후, 할당하지 않았을 때 기본값. 연산하면 NaN이 됨. typeof 는 ‘undefined’

```jsx
let variable // -> undefined
```

# 12. eqeq 줄이기

eqeq: js에서 동등연산자를 의미, ‘==’

‘==’ : Equality. 자동 형변환(type casting)이 됨.

‘===’ : Strict equality

**⇒ 형변환은 수동으로해서 ‘===’을 사용하기**

# 13. 형변환 주의하기

명시적인 형변환을 하자. 예측할 수 있는 형변환을 사용해야함.

```jsx
11 + '문자와 결합' // '11 문자와 결합'
-> Sting(11 + '문자와 결합')

!!'문자열' // true
-> Boolean('문자열')
!!'' // flase
-> Boolean('')

parseInt('9.9999', 10) // 9
Number('11) // 11
```

# 14. isNaN

컴퓨터는 2진수를 사용한다. 소수점이 요상~

js에서는 IEEE 754 부동소수점을 이용함.

```jsx
isNaN(123) // false -> 123은 숫자가 아닌게 아니다 -> 숫자임;; 아주 헷갈린다
isNaN(123 + 'text') // true -> 숫자가 아니라는 것을 검사하기 어려움

// ES2015+
Number.isNaN(123 + 'text') // false 
```

`Number.isNaN()`으로 검사하면 엄격한 검사를 할 수 있음.
