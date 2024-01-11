# Questions 

Detailed explanation is in [ANSWERS-ENG.md](./ANSWERS-ENG.md).   
Пошаговое решение в [ANSWERS-RU.md](./ANSWERS-RU.md).

- Question 1
```Javascript
console.log('start');

const promise1 = new Promise((resolve, reject) => {
  console.log(1)
})

console.log('end');
```

<details>
<summary>Answer</summary>
start, 1, end
</details>

- Question 2
```Javascript
console.log('start');

const promise1 = new Promise((resolve, reject) => {
  console.log(1)
  resolve(2)
})

promise1.then(res => {
  console.log(res)
})

console.log('end');
```

<details>
<summary>Answer</summary>
start , 1 , end и 2
</details>

- Question 3
```Javascript
console.log('start');

const promise1 = new Promise((resolve, reject) => {
  console.log(1)
  resolve(2)
  console.log(3)
})

promise1.then(res => {
  console.log(res)
})

console.log('end');
```

<details>
<summary>Answer</summary>
start , 1 , 3 , end и 2
</details>

- Question 4
```Javascript
console.log('start');

const promise1 = new Promise((resolve, reject) => {
  console.log(1)
})

promise1.then(res => {
  console.log(2)
})

console.log('end');
```

<details>
<summary>Answer</summary>
start , 1 , end 
</details>

- Question 5
```Javascript
console.log('start')

const fn = () => (new Promise((resolve, reject) => {
  console.log(1);
  resolve('success')
}))

console.log('middle')

fn().then(res => {
  console.log(res)
})

console.log('end')
```

<details>
<summary>Answer</summary>
start , middle, 1 , end и success 
</details>

- Question 6
```Javascript
console.log('start')

Promise.resolve(1).then((res) => {
  console.log(res)
})

Promise.resolve(2).then((res) => {
  console.log(res)
})

console.log('end')
```

<details>
<summary>Answer</summary>
start , end , 1 и 2 
</details>

- Question 7
```Javascript
console.log('start')

setTimeout(() => {
  console.log('setTimeout')
})

Promise.resolve().then(() => {
  console.log('resolve')
})

console.log('end')
```

<details>
<summary>Answer</summary>
start , end , resolve и setTimeout
</details>

- Question 8
```Javascript
const promise = new Promise((resolve, reject) => {
  console.log(1);
  setTimeout(() => {
    console.log("timerStart");
    resolve("success");
    console.log("timerEnd");
  }, 0);
  console.log(2);
});

promise.then((res) => {
  console.log(res);
});

console.log(4);
```

<details>
<summary>Answer</summary>
1, 2, 4, timeStart, timeEnd, success
</details>

- Question 9
```Javascript
const timer1 = setTimeout(() => {
  console.log('timer1');
  
  const promise1 = Promise.resolve().then(() => {
    console.log('promise1')
  })
}, 0)

const timer2 = setTimeout(() => {
  console.log('timer2')
}, 0)
```

<details>
<summary>Answer</summary>
timer1, promise1, timer2
</details>

- Question 10
```Javascript
console.log('start');

const promise1 = Promise.resolve().then(() => {
  console.log('promise1');
  const timer2 = setTimeout(() => {
    console.log('timer2')
  }, 0)
});

const timer1 = setTimeout(() => {
  console.log('timer1')
  const promise2 = Promise.resolve().then(() => {
    console.log('promise2')
  })
}, 0)

console.log('end');
```

<details>
<summary>Answer</summary>
start, end, promise1, timer1, promise2, timer2
</details>

- Question 11
```Javascript
async function asyncFunc() {
  console.log(2);
  await Promise.resolve();
  console.log(4);
}
console.log(1);
asyncFunc();
console.log(3);
```

<details>
<summary>Answer</summary>
1, 2, 3, 4
</details>

- Question 12
```Javascript
Promise.resolve(1)
  .then(2)
  .then(Promise.resolve(3))
  .then(console.log);
```

<details>
<summary>Answer</summary>
1
</details>

- Question 13
```javascript
console.log('first');
setTimeout(() => console.log('second'), 0);
new Promise((resolve, reject) => {
  console.log('third');
  resolve();
}).then(() => console.log('fourth'));
console.log('fifth');
```

<details>
<summary>Answer</summary>
first, third, fifth, fourth, second
</details>

- Question 14
```javascript
setTimeout(() => console.log("1"), 0);
new Promise((resolve, reject) => {
  console.log("2");
  for (let i = 0; i < 10000; i++) {
    if (i === 9999) resolve();
  }
  console.log("3");
}).then(() => console.log("4"));
console.log("5");
```

<details>
<summary>Answer</summary>
2, 3, 5, 4, 1
</details>

- Question 15
```javascript
Promise.reject('error')
  .then(res => console.log('success:', res), err => console.log('fail:', err))
```

<details>
<summary>Answer</summary>
fail: error
</details>

- Question 16
```javascript
async function func() {
  console.log(1);
  await new Promise(resolve => setTimeout(resolve, 1000));
  console.log(3)
}
console.log(2);
func();
console.log(4);
```

<details>
<summary>Answer</summary>
2, 1, 4, 3
</details>

- Question 17
```javascript
Promise.resolve()
  .then(() => {
    console.log('then1');
    Promise.resolve().then(() => console.log('then1.1'));
  })
  .then(() => console.log('then2'));
```

<details>
<summary>Answer</summary>
then1, then1.1, then2
</details>

- Question 18
```javascript
setTimeout(() => console.log('a'), 0);
Promise.resolve().then(() => console.log('b')).then(() => console.log('c'));
```

<details>
<summary>Answer</summary>
b, c, a   
</details>

- Question 19
```javascript
console.log('start');
setTimeout(() => console.log('setTimeout'), 0);
Promise.resolve().then(() => console.log('promise'));
console.log('end');
```

<details>
<summary>Answer</summary>
start, end, promise, setTimeout
</details>

- Question 20
```javascript
async function test() {
  console.log(1);
  await async function() { console.log(2) }();
  console.log(3);
}
console.log(4);
test();
console.log(5);
```
<details>
<summary>Answer</summary>
4, 1, 2, 5, 3
</details>
