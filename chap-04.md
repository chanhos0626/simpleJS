---
description: '제어문중에 하나인 반복문에 대해서 알아보겠습니다 :)'
---

# 04. 반복문

![](.gitbook/assets/body%20%282%29.png)

## 반복문

이번 시간에는 반복문을 살펴보겠습니다. 반복문 말그대로 코드를 반복해주는 친구들입니다. 반복문은 아래와 같이 3가지의 종류가 있습니다.

* for
* while
* do\_while
* continue \(보조\)

### for 문

일정 횟수만큼 조건에 따라 반복 실행하여야 할 때 사용합니다.

```javascript
for(초기값; 조건; 증감식){
  // 반복 구문
}
```

> 간단한 문제  
> 1 - 10까지 출력하시오

반복문을 쓰지 않고 위의 문제를 해결하려 한다면 코드는 아래와 같을 거에요

```javascript
console.log(1);
console.log(2);
console.log(3);
// .... console.log(4 ~ 10);
```

10이면 console.log 가 10개 100 이면 100개의 코드가 반복됩니다.

```javascript
for (var i = 1; i <= 10; i += 1){
  console.log(i); // 이렇게 한줄로 끝낼수 있어요
}
```

반복문을 이용한다면 간단하게 해결됩니다. 위 코드의 실행 순서는 아래와 같습니다.

1. 초기값은 1입니다. 
2. 조건을 비교합니다. 1 &lt;= 10 은 true 이기 때문에 console.log\(i\) 를 실행합니다.
3. 증감식으로 이동합니다. i = i + 1 가 실행되고 1이 증가하여 i는 2가 됩니다.
4. 1 ~ 3번을 반복합니다. 조건식이 false가 될때 반복문은 종료됩니다. 

### while

while 은 조건이 false 가 될 때 까지 반복합니다.

```javascript
while(조건){
  // 반복구문
}
```

만약에 조건값이 true로 떨어진다면 **while** 은 끝나지 않고 계속 실행됩니다.  
이것을 **무한루프**라고 부릅니다. while을 쓰실때는 종료시점을 잘 맞춰주셔야 됩니다.

```javascript
// 궁금하시다면 이 구문을 개발자 도구에서 실행시켜보세요 
var i = 0;
while(true){
  console.log(i);
  i += 1;
}
```

### do-while

**do-while** 도 **while**문 입니다. 왜 do가 붙었냐면 do-while은 **무조건 1번은 실행**하고 조건을 비교해 while문을 실행할지 말지 판단하기 때문입니다.

```javascript
var i = 10;
do {
  console.log(i); // 무조건 한번은 실행이 됩니다
  i += 1;
} while (i < 5); // 종료 조건을 걸어줍니다.
```

위의 경우 i 가 10 이기 때문에 10 &lt; 5 는 성립하지 않습니다.  
하지만 do 영역은 무조건 한번은 실행되기 때문에 console 에 10이 찍힙니다.

### continue

continue를 만나면 이후 구문 실행을 생략하고 조건검사 위치로 이동합니다.

> 간단한 문제  
> 2를 제외한 0 ~ 4 까지 수를 출력 하세요

```javascript
for (var i = 0; i < 5; i++) {
  if(i === 2){ // 2일 때는 건너뜁니다.
    continue; // continue를 만나면 아래 console 은 실행되지 않습니다.
  }
  console.log(i);
}
```

### For vs While

for와 while은 둘다 반복문 입니다. for 로 만들어진걸 while 로 변경할 수 있고 while 만들어진걸 for로 변경하는 것도 가능합니다.  
그렇다면 차이점은 무엇일까요 ?

#### 실행의 순서

for 는 초기값 =&gt; 조건 =&gt; 실행 =&gt; 증감식의 순서로 실행이 됩니다.  
while 의 경우 조건만 비교를 한 후 실행을 시키기 때문에 for 보다 while 의 속도가 빠릅니다.

#### 범위에 대한 처리

for 문 같은 경우 for문 자체에서 범위에 대한 처리가 가능합니다.

```javascript
for (var i = 0; i < 10; i += 1) {
    console.log(i);
}
```

범위에 대한 처리 \( ex. 1 ~ 10 \) 이라는 처리를 while 문 조건에서 처리할 수 없습니다.  
밖에서 처리를 해줘야합니다. while 은 조건을 비교한 후 while 영역 안에서 후처리를 합니다.

```javascript
var i = 0; // 범위에 대한 설정을 위해 while 문 밖에 변수를 선언
while (i < 5) {
    console.log(i);
    i += 1; // while 영역 안에서 i 에 대한 후처리를 한다.
}
```

### 예제

> 간단한 문제1  
> 라이언은 카카오중학교 학생이다. 라이언은 국어 78점을 맞았다. 라이언의 등급을 출력하시오 \(80이상 A, 70이상 B, 69이상 C\)
>
> 간단한 문제2  
> 라이언은 1~30 사이의 숫자중 짝수들의 숫자만 더하는 프로그램을 만들고싶다. 1 ~ 30 사이의 수들중 짝수만 골라내어 합산하는 프로그램을 만들어봅시다.

**정답**: [https://jsfiddle.net/gaffd2k6/](https://jsfiddle.net/gaffd2k6/)
