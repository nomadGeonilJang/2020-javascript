# Javascript 2020

## Javascript 2020시작하기

1. 2019에 공부했던 내용에 추가하는 작업을 진행합니다.

## 1️⃣ 변수 선언

### 1. var의 문제점

- 정의된 변수가 함수 스코프를 가진다.

  ```javascript
  function fnc() {
    var i = 1;
  }
  console.log(i); //error
  ```

- 선언문을 작성하지 않으면 전역변수가 되버린다.
  ```javascript
  function fnc1() {
    i = 1;
  }
  function fnc2() {
    console.log(i);
  }
  fnc1();
  fnc2(); //1
  ```
- 호이스틍이 발생한다.
  - 선언부가 실행 컨텍스트 최상단으로 올려지는 현상.
  - environmentRecord

### 2. const, let

- Block Scope를 가진다.
- 호이스팅이 동일하게 발생이 되지만 값이 할당이 되지 않은 상태.
  - var의 경우는 undefined가 할당이 됩니다.
- const 변경 불가능한 상수를 만든다. (상수: 재할당이 불가능한다.)
- let 변경이 가능한 변수를 만든다. (변수: 재할당이 가능하다.)

## 2️⃣ 타입

### 1. javascript의 8개의 기본타입

- typeof를 사용하면 오른쪽 값의 타입을 반환한다.
- 1️⃣ number, 2️⃣ bigint, 3️⃣ string, 4️⃣ boolean, 5️⃣ object, 6️⃣ symbol, 7️⃣ undefined, 8️⃣ null
- String, Number, BigInt, Booolean 형변환을 할 때 사용이이 가능합니다.
- symbol 유일한 값을 만든다.
- === (값과 타입모두 비교), == (타입을 변환화면서 까지 비교한다.)

  ```javascript
  const val1 = 1;
  const val2 = 100000000000000000000000000n;
  const val3 = "hello, world";
  const val4 = true; // false
  console.log(typeof val1, typeof val2, typeof val3, typeof val4);
  //number bigint string boolean

  const val5 = { name: "hello javascript" };
  const val6 = Symbol("hello");
  const val7 = undefined;
  const val8 = null;
  console.log(typeof val5, typeof val6, typeof val7, typeof val8);
  //object symbol undefined object(버그 수정 안된 상태)

  function fnc1() {}
  console.log(typeof fnc1);
  //function

  console.log(typeof []);
  //object
  ```
