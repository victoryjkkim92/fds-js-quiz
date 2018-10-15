### 문제 1

두 정수 `start`, `end`를 입력받아, `start`부터 `end`까지의 모든 정수를 배열로 반환하는 함수를 작성하세요.

예:
```
range(3, 6); -> [3, 4, 5, 6]
```

* 접근방법
  + 새로운 배열 반환해야하니까 
  + 빈 배열을 변수로 선언한 다음에 거기에 요소들을 추가해줌 .push()메소드 사용
  + for문은 첫번째 인자로 들어온 값부터 두번째까지 포함되게 돌려줘야함

```js

function range(start, end) {
  const numbers = [];
  for (let i = start; i <= end; i++) {
    numbers.push(i);
  }
  return numbers;
}
range(3, 6); 
```

### 문제 2

수 타입의 값으로만 이루어진 배열을 입력받아, 그 값들의 합을 구하는 함수를 작성하세요.

```js
reduce 메소드 사용
function arrSum(input){
  const arr = input;
  return arr.reduce((acc, item) => acc + item, 0);
}


arrSum([1, 2, 3, 4, 5]); // 15
```

```js
루프 사용
function arrSum(input) {
  let memory = 0;
  for (let i = 0; i < input.length; i++) {
    memory += input[i];
  }
  return memory;
}

arrSum([1, 2, 3, 4, 5]);
```

### 문제 3

배열을 입력받아, falsy인 요소가 제거된 새 배열을 반환하는 함수를 작성하세요.

```js

function removeFalsy(arr) {
  let newArr = [];
  for (let i = 0; i < arr.length; i++){
    if (arr[i]) {
      newArr.push(arr[i]);
    }
  }
  return newArr;
}

removeFalsy([0, 1, null, 3, false]);
```

### 문제 4

배열을 입력받아, 중복된 요소가 제거된 새 배열을 반환하는 함수를 작성하세요.

```js
function removeDuplicates(arr){
  let memory =[];
  for (let i = 0; i < arr.length; i++){
    if (!memory.includes(arr[i])){
      memory.push(arr[i]);
    }
  }
  return memory;
}
removeDuplicates(['hello','world','hello', 'great'])
```

* set을 사용하는 방법

```js
function removeDuplicates(arr){
  const set = new Set(arr)
  return Array.from(set)
}
removeDuplicates([1,2,3,2,1])
```


### 문제 5

수 타입의 값으로만 이루어진 두 배열을 입력받아, 다음과 같이 동작하는 함수를 작성하세요.
- 두 배열의 같은 자리에 있는 요소를 더한 결과가 새 배열의 요소가 됩니다.
- 만약 입력받은 두 배열의 길이가 갖지 않다면, 긴 배열에 있는 요소를 새 배열의 같은 위치에 포함시키세요.

예:
```
addArray([1, 2, 3], [4, 5, 6, 7]) -> [5, 7, 9, 7]
```


```js
function addArray(arr1, arr2) {
  const memory = [];
  if (arr1.length > arr2.length) {
    for (let i = 0; i < arr1.length; i++) {
      memory.push(arr1[i] + arr2[i]);
      arr2.push(0);
    }
  } else {
    for (let i = 0; i < arr2.length; i++) {
      memory.push(arr1[i] + arr2[i]);
      arr1.push(0);
    }
  }
  return memory;
}

addArray([1, 2, 3, 5, 7, 8], [2, 3, 4, 8, 8]);
```

### 문제 6

배열을 입력받아, 배열의 요소 중 두 개를 선택하는 조합을 모두 포함하는 배열을 작성하세요.

예:
```
combination([1, 2, 3]); -> [[1, 2], [1, 3], [2, 3]]
```

```js
function selectTwo(arr) {
  const newArr = [];
  for (let i = 0; i < arr.length; i++) {
    for (let j = i; j < arr.length; j++){
      if(arr[i] !== arr[j]){
      newArr.push([arr[i], arr[j]]);
      }
    }
  }
  return newArr;
}
selectTwo([1, 2, 3, 4, 5]);
```

### 문제 7

'금액'과 '동전의 종류가 들어있는 배열'를 입력받아, 최소한의 동전을 사용해서 금액을 맞출 수 있는 방법을 출력하는 함수를 작성하세요.
(단, 동전의 종류가 들어있는 배열에는 큰 동전부터 순서대로 들어있다고 가정합니다.)

예:
```
coins(263, [100, 50, 10, 5, 1]);
// 출력
100
50
10
1
1
1
```

```js
function coins(money, arr){
  for(let i =0; i< arr.length;i++){
    if(money - arr[i] >= 0) {
      money -= arr[i]
      console.log(arr[i]);
      i-=1
    } 
  }
  return money;
}
coins(263, [100, 50, 10, 5, 1])
```

### 문제 8

수 타입의 값만 들어있는 배열을 입력받아, 해당 배열을 오름차순 정렬하는 함수를 작성하세요. (`Array.prototype.sort`를 사용하지 않고 작성해보세요. [선택 정렬](https://ko.wikipedia.org/wiki/%EC%84%A0%ED%83%9D_%EC%A0%95%EB%A0%AC)을 참고하세요.)
