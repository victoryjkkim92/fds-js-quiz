### 문제 1

두 수를 입력받아 큰 수를 반환하는 함수를 작성하세요.

* 방법 1

```js
function larger(x, y){ // 매개변수(parameter)
  const a = x
  const b = y
  let c;

  // a가 크면 a를 c에 넣고, 아니면 b를 c에 넣는다.

  if (a > b){
    c = a;
  } else {
    c = b;
  }
  return(c);
}
```

* 방법 2 

```js
  function larger(x,y){
    if (x > y){
      c = x
    } else {
      c = y
    }
    return c;
  }

  console.log(larger(3,2)); // 
```

* 방법 3

```js
  function larger(x,y){
    if (x > y){
      return x;
    } else {
      return y;
    }
  }
  console.log(larger(3,4));
```

* 방법 4

```js
  function larger(x,y){
    return x > y ? x: y;
  }
  console.log(larger(3,4));
```


### 문제 2

세 수를 입력받아 그 곱이 양수이면 `true`, 0 혹은 음수이면 `false`, 둘 다 아니면 에러를 발생시키는 함수를 작성하세요.

에러를 발생시키는 코드는 다음과 같습니다.

```js
throw new Error('입력값이 잘못되었습니다.');
```

* 방법 1

```js

function isPositive(x,y,z){
  if (x * y * z > 0) {
    return true;
  } else if(x * y * z <= 0){
    return false;
  } else {
    throw new Error('입력값이 잘못되었습니다.');
  }
}
// console.log(isPositive(1,2,3));  // 반환값 : true
// console.log(isPositive(1,2,-3)); // 반환값 : false
// console.log(isPositive(1,2,'haha')); // 반환값 : '입력값이 잘못되었습니다.'
```

### 문제 3

세 수 `min`, `max`, `input`을 입력받아, 다음과 같이 동작하는 함수를 작성하세요.
- `min`보다 `input`이 작으면, `min`을 반환합니다.
- `max`보다 `input`이 크면, `max`를 반환합니다.
- 아니면 `input`을 반환합니다.

예:
```
limit(3, 7, 5); -> 5
limit(3, 7, 11); -> 7
limit(3, 7, 0); -> 3
```

* 방법 1

```js

function limit(min,max,input){
  if (min > input) {   
    return min;   // `min`보다 `input`이 작으면, `min`을 반환
  } else if (max < input) {
      return max;  // `max`보다 `input`이 크면, `max`를 반환합니다.
    } else {
      return input; // 아니면 `input`을 반환합니다.
    }
}

// console.log(limit(3,7,5)); 반환값 : 5
// console.log(limit(3, 7, 11)); 반환값 : 7
// console.log(limit(3, 7, 0)); 반환값 : 3


```

### 문제 4

어떤 정수가 짝수인지 홀수인지 출력하는 함수를 작성하세요. 이를 이용해서, 1부터 20까지의 수가 각각 짝수인지 홀수인지 출력하는 프로그램을 작성하세요.

* 방법 1

```js

function evenOrOdd(x){
  if (x % 2 === 0){
    console.log('x: 짝수');   // 만약 x가 짝수면 'x: 짝수'라고 출력
  }
  else {
    console.log('x: 홀수');  // 아니면 'x:홀수'라고 출력
  }
}

// 이를 이용해서, 1부터 20까지의 수가 각각 짝수인지 홀수인지 출력하는 프로그램을 작성하세요.

for(let i = 0; i< 20; i++){
  evenOrOdd(i+1) // i+1이라고 해주지않으면 초기값인 0부터 시작
}

```

* 문자열 이어붙이기 | 만약 어떤 수를 출력하고싶은지 또한 화면 출력을 원할 때_1 *

```js

function evenOrOdd(x){
  if (x % 2 === 0){
    console.log('x: 짝수');   // 만약 x가 짝수면 'x: 짝수'라고 출력
  }
  else {
    console.log('x: 홀수');  // 아니면 'x:홀수'라고 출력
  }
}

// 이를 이용해서, 1부터 20까지의 수가 각각 짝수인지 홀수인지 출력하는 프로그램을 작성하세요.

for(let i = 0; i< 20; i++){
  evenOrOdd(i+1)
}
```

* 문자열 이어붙이기 | 만약 어떤 수를 출력하고싶은지 또한 화면 출력을 원할 때_2 *

```js
function evenOrOdd(x){
  if (x % 2 === 0){
    console.log(x + ': 짝수');  // 만약 x가 짝수면 'x: 짝수'라고 출력
    // 만약 '짝수 2 짝수'를 표현하기 위해선  '짝수' + x +'짝수'를 해야하지만,
  }
  else {
    console.log(`${x}: 홀수`);
    // 탬플렛리터럴 _ 백틱(`) _ 을 사용할 땐 `홀수 ${x} 홀수`만 해도 된다용
  }
}

// 이를 이용해서, 1부터 20까지의 수가 각각 짝수인지 홀수인지 출력하는 프로그램을 작성하세요.

for(let i = 0; i< 20; i++){
  evenOrOdd(i+1)
}
```


### 문제 5

100 이하의 자연수 중 3과 5의 공배수를 모두 출력하는 프로그램을 작성하세요.

* 접근방법
  
  + 100이하의 자연수  :  for문 사용해서 초기값은 1, 범위는 100보다 같거나 작다, 1씩 증가
  + 3과 5의 공배수 : 3으로 나누어도 나머지 0, 5로 나누어도 나머지 0 | 두 경우 다 적용되어야 하니까 '&&' and 연산자 사용
  + 출력 : console.log()

```js

for(let i = 1; i<=100; i++){ // 초기값 : 1 | 반복 횟수 100보다 작거나 같은 자연수 
  if (i % 3 === 0 && i % 5 === 0){ // 3과 5의 공배수 : 3과 5로 나눴을 경우 두 경우 모두의 나머지가 0이어야 해서 '&&'사용 
    console.log(i); // 화면에 출력시킴
  }
}

```

### 문제 6

자연수를 입력받아, 그 수의 모든 약수를 출력하는 함수를 작성하세요.

* 접근방법
  
  + 함수 작성
  + 자연수 : for문 사용해서 초기값은 1(입력되는 수 n을 나누는 자연수), 반복횟수, 1씩 증가
  + 모든 약수 : n(매개변수)이 i로 나누어졌을 때 나머지가 0일때
  + 출력 : console.log()
  + 함수 호출


입력받은 값의 약수만 출력하고 싶을 때

```js

function divide(n){
  for(i=1; i<=n; i++){
    if(n % i === 0){
      console.log(i);
    }
  }
}

divide(20);  // 출력값 : 1,2,4,5,10,20 (20의 약수)
```

입력받은 값은 약수를 모두 출력해서 약수인지 아닌지 확인해 보고 싶을경우

```js

 function divide(n){
   for(i=1; i<=n; i++){
    if(n % i === 0){
      console.log(`${i} : 약수`);
    } else{ 
        console.log(`${i} : 약수 아님`);
    }
  }
}

// divide(4);  
// 출력값 : 
// 1 : 약수
// 2 : 약수
// 3 : 약수 아님
// 4 : 약수

```



### 문제 7

2 이상의 자연수를 입력받아, 그 수가 소수인지 아닌지를 판별하는 함수를 작성하세요.

* 접근방법
  
  + 함수 작성
  + 2 이상의 자연수 : for문 사용해서 초기값은 2, 반복횟수 , 1씩 증가
  + 소수인지 아닌지 판단 : 소수는 1과 자신을 제외한 어떠한 정수로도 나누어 지지 않는 수
  + 함수 호출


```js

function prime(n){
  for(let i=2; i<n; i++){
    if( n % i === 0 ){
      return '소수 아님';
    } else {
      return '소수';
    }
  }
}

prime(7); // 반환값 : '소수'

```

선생님 코드
```js
function isPrime(x){
  // 소수 : 1과 자기 자신 밖에 약수가 없는 수 
  // -> 1과 자기자신이 아닌 약수가 하나라도 있으면 소수가 아니다. 
  for(let i = 2; i < x; i++){
    if (x % i === 0){
      return false
    }
  }
  return true
}
isPrime(2) // false
```


### 문제 8

1부터 100까지의 수를 차례대로 출력하되, 자릿수에 3, 6, 9중 하나라도 포함되어 있으면 '짝!'을 대신 출력하는 프로그램을 작성하세요.

* 접근방법
  
  + 출력하는 프로그램이라고 했기 때문에 : console.log();사용 | 함수 작성 노노
  + 1 부터 100까지 수 : for문에서 i의 초기값을 1, 100이거나 작을때까지 돌림, 1씩 커짐
  + 입력되는 매개변수를 string타입으로 바꿔주고, 3,6,9가 포함되어있는지 .includes()메소드를 사용해 확인
  + 만약 있으면 '짝'이라고 출력, 없으면 그냥 i값 출력
  
내코드

```js

  for(i=1; i<=100; i++){
    const num = i.toString()
    if(num.includes('3') || num.includes('6') || num.includes('9')){ 
      console.log('짝!');
    } else {
        console.log(i);
      }
  }
```

선생님 코드

```js
for(i=0; i<100; i++){
  const num = i + 1;
  const str = num.toString()
  if(str.includes('3') || str.includes('6') || str.includes('9')){ 
    console.log('짝!');
  } else {
      console.log(num);
    }
}
```

### 문제 9

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

* 접근방법 

  + 출력하는 함수를 작성하세요 : console.log(); 사용 | function starPattern(n){}
  + 양의 정수를 입력받아 : for문 작성 _ for(i = 1; i <= n; i ++ ){}
  + 별 출력 : 'string타입'.repeat() 메소드 사용! 
  + 그러기 위해선 -> const star = '* '라는 변수 선언

```js
function starPattern(n){
  const star = "* "
  for (i = 1; i <=n; i++){
    console.log(star.repeat(i));
  }
}

starPattern(1);
starPattern(3);
starPattern(5);
```

```js
// 중첩루프사용
function print(height){
  for(let i = 0; i <height; i++){
      //한 줄 출력
    let stars = ''
    for(let j = 0; j < i + 1; j++){
      // 별 표 하나를 출력
    stars += '* '
    }
    console.log(stars)
  }
}
```

1을 입력받은 경우:
```
*
```

3을 입력받은 경우:
```
*
* *
* * *
```

5를 입력받은 경우:
```
*
* *
* * *
* * * *
* * * * *
```

### 문제 10

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

* 접근 방법
 
   + 출력하는 함수를 작성 : console.log() | function starPattern(n){}
   + 양의 정수를 입력받아 : 하나씩 돌려야 하니까 for문 사용

      초기값 1, 반복횟수_ 위아래로 출력되야하니까 n두번 곱한거보다 작을때까지, 1씩 커짐
   + 별도 필요하고 빈칸도 필요하니까 둘 다 변수 선언 해야 할 것 같음
   + 그럼 이걸 가지고 if문 사용해서 조건을 정함 어째 정하지...
   + i가 n보다 작거나 같을때 ->  빈칸은 n-i 만큼, 별은 i 만큼 출력 
   + i가 n보다 클때 -> 빈칸은 i-n 만큼, 별은 n*2한거에서 i뺀 만큼 출력 [이부분이 제일 어려웠음]

```js

function starPattern(n){
  const blank = " ";
  const star = "* ";
  for (let i = 1; i < 2*n; i++){
    if (i <= n){
      console.log(blank.repeat(n-i)+star.repeat(i));
    } else {
      console.log(blank.repeat(i-n)+star.repeat(2*n-i));
    } 
  }
}
starPattern(5);
```

선생님 코드 

```js
function print(height){
  for (i = 0; i < height; i++){
    const n = i + 1;
    const line = ' '.repeat(height-n) + '* '.repeat(n)
    console.log(line)
  }
  for (i = height-2; i >=0; i--){
    const n = i + 1;
    const line = ' '.repeat(height-n) + '* '.repeat(n)
    console.log(line)
  }
}

print(3)
```

함수 사용하기

```js
function printLine(height, i) {
  const n = i + 1;
  const line = ' '.repeat(height - n) + '* '.repeat(n)
  console.log(line)
}

function print(height) {
  for (i = 0; i < height; i++) {
    printLine(height, i)
  }
  for (i = height - 2; i >= 0; i--) {
    printLine(height, i)
  }
}

print(3)
```



1를 입력받은 경우:
```
*
```

3를 입력받은 경우:
```
  *
 * *
* * *
 * *
  *
```

5를 입력받은 경우:
```
    *
   * *
  * * *
 * * * *
* * * * *
 * * * *
  * * *
   * *
    *
```

### 문제 11

두 수를 입력받아서, 두 수의 최대공약수를 반환하는 함수를 작성하세요. ([유클리드 호제법](https://ko.wikipedia.org/wiki/%EC%9C%A0%ED%81%B4%EB%A6%AC%EB%93%9C_%ED%98%B8%EC%A0%9C%EB%B2%95)을 참고하세요.)

### 문제 12

세 수를 입력받아 큰 것부터 차례대로 출력하는 함수를 작성하세요.

### 문제 13

자연수 `n`을 입력받아, `n`번째 피보나치 수를 반환하는 함수를 작성하세요.
