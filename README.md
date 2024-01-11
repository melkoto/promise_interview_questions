# Questions 

- Question 1
```Javascript
console.log('start');

const promise1 = new Promise((resolve, reject) => {
  console.log(1)
})

console.log('end');
```

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

- Question 12
```Javascript
Promise.resolve(1)
  .then(2)
  .then(Promise.resolve(3))
  .then(console.log);
```

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

- Question 15
```javascript
Promise.reject('error')
  .then(res => console.log('success:', res), err => console.log('fail:', err))
```

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

- Question 17
```javascript
Promise.resolve()
  .then(() => {
    console.log('then1');
    Promise.resolve().then(() => console.log('then1.1'));
  })
  .then(() => console.log('then2'));

```

- Question 18
```javascript
setTimeout(() => console.log('a'), 0);
Promise.resolve().then(() => console.log('b')).then(() => console.log('c'));

```

- Question 19
```javascript
console.log('start');
setTimeout(() => console.log('setTimeout'), 0);
Promise.resolve().then(() => console.log('promise'));
console.log('end');

```

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
