### 문제 1

양수를 입력받아 이 수를 반지름으로 하는 원의 넓이를 반환하는 함수를 작성하세요.

* 접근방법
  + 원의 넓이 구하는 공식 
  + 넓이 = 파이 * 반지름제곱

```js
function circleWidth(num){
  return Math.PI*Math.pow(num,2)
}
circleWidth(6)
```

### 문제 2

두 정수 `min`, `max` 를 입력받아, `min` 이상 `max` 미만인 임의의 정수를 반환하는 함수를 작성하세요.

* 접근방법
  + 함수 : function randomInteger(min, max){}
  + min이상 max미만인  (max-min)까지 랜덤반환하는데 min이상이어야 하니까 min더해줌
  + 임의의 정수 반환 Math.random()쓰면 부동소수점으로 값을 반환해주기때문에 Math.floor()를 써서 소수점 뒤에 내림!

```js
function randomInteger(min, max){
  return Math.floor(Math.random() * (max - min))+ min;
}
randomInteger(5, 11); // 반환값 : 5,6,7,8,9,10 중에 하나
```



### 문제 3

정수를 입력받아, 5 단위로 올림한 수를 반환하는 함수를 작성하세요.

예:
```
ceilBy5(32); -> 35
ceilBy5(37); -> 40
```
* 접근방법

  + 소수점 아래를 올림해주는 메소드 (Math.ceil())을 어떻게 사용할까 고민하다가 5로 나눠주면 뒤에 소수점이 생길 수 밖에 없으니까 그걸 올림해서 다시 5를 곱해주면 된다고 생각함

```js
function ceilBy5(num){
  return Math.ceil(num / 5) * 5;
}
ceilBy5(32);
ceilBy5(37);
```


### 문제 4

배열을 입력받아, 요소들의 순서를 뒤섞은 새 배열을 반환하는 함수를 작성하세요.

### 문제 5

임의의 HTML 색상 코드를 반환하는 함수를 작성하세요.

* 접근 방법

  + HTML 색상 코드는 16진수 사용하니까 '0123456789abcdef'를 변수의 값으로 선언해주고 Math.random()메소드를 사용하면 된다고 생각함
  + Math.random()는 Math.ceil()아니면 Math.floor()이랑 짝궁이니까 둘 중 하나 선택해서 사용하기로함
  + for문으로 6자리만큼 돈 다음 빈 메모리에 추가해줌

```js
function randomHtmlColor(num){
  const numberRange = '0123456789abcdef';
  // 색상표기법 
  let memory = '#'
  for(let i = 0; i < 6; i++){
    memory += numberRange[Math.floor(Math.random()*16)];
  }
  return memory;
}
randomHtmlColor();
```

### 문제 6

양수를 입력받아, 그 수만큼의 길이를 갖는 임의의 문자열을 반환하는 함수를 작성하세요.

* 접근방법

  + 양수를 입력받아서 임의의 문자열을 반환해야해서 알파벳을 문자열을 변수로 선언해주고
  + 그 안에서 입력받은 양수만큼 for문 돌림
  + 빈 메모리에 추가 랜덤으로 문자열추가해줌

```js
function sameLengthWord(num){
  const strSample = 'abcdefghijklmnopqrstuvwxyz';
  let memory = ''
  for(let i = 0; i < num; i++){
    memory += strSample[Math.floor(Math.random()* num)]
  }
  return memory;
}
sameLengthWord(20);
```

### 문제 7

수 타입의 값으로만 이루어진 배열을 입력받아, 그 값들의 표준편차를 구하는 함수를 작성하세요.

```js

function stdDev(arr) {
  // arr의 평균 구하기
  const sum = arr.reduce((acc, item) => acc + item, 0)
  const mean = sum / arr.length
  console.log(`mean:${mean}`)
  // 각 요소에 대한 편차 구하기 (편차 = 값 - 평균)
  const ps = arr.map(item => item - mean)
  console.log(`ps: ${ps}`)
  // 각 요소에 대해 제곱하기
  const powers = ps.map(item => item **2)
  // 위 제곱한 배열의 평균 구하기
  const vv = powers.reduce((acc, item) => acc + item, 0) / powers.length
  console.log(`vv : ${vv}`)
  // 루트 씌우기
  return Math.sqrt(vv)
}

stdDev([1, 2, 3, 4, 5]);
```
