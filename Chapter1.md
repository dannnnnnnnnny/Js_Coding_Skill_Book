# 1. const로 변하지 않는 값을 표현하기
- 과거 js의 변수 할당 방법은 var 하나 였음
- 현재 let, const, var 3가지가 존재하며 사용법도 다름
---
- const는 가장 적은 것을 할 수 있기 때문에 좋다.
- 코드를 읽기 쉽게 만드는 제약 사항을 가지고 있다.
- 블록 내에서 재할당할 수 없는 변수 선언이다.
- 한번 선언하면 변경할 수 없다. (But, 불변값이 되는 것은 아님)

- 코드를 훑어볼 때 해당 변수를 신경쓰지 않아도 된다고 알려줄 수 있다.
### 1)
```js
const taxRate = 0.1;
const total = 100 + (100 * taxRate);
// 어쩌구 저쩌구 100줄이 넘었다...
return `총합 ${total}`;
```
### 2)
```js
var taxRate = 0.1;
var total = 100 + (100 * taxRate);
// 어쩌구 저쩌구 100줄이 넘었다...
return `총합 ${total}`;
```
- 1) 코드는 중간에 몇줄의 코드가 있다고 하더라도 total은 110이란 것을 예상할 수 있다.
- 2) var 변수는 변할 수 있기 때문에 어떤 값이 됐을지 예상하기 힘들다.

---
- const는 변수는 재할당할 수 없지만, 값은 바꿀 수 있다. 할당된 값은 불변값이 되지 않는다.
```js
const arr = [];
for (let i = 0; i < nums.length; i++) {
  if (nums[i].isOkay) {
    arr.push(nums[i]);
  }
}
```
- 이는 완벽하게 작동되는 코드다.

```js
const arr = nums.filter(item => item.isOkay);
```
- 이와 같은 코드이며 같은 결과를 가지지만 조작을 사용하지는 않는다.

---
## 결론
## const를 Default 기본으로 사용하자.