# **Complete Guide to JavaScript Array Methods**

This guide covers **all** JavaScript array methods, grouped by their behavior, with detailed explanations and **code examples**.

---

# **1. Methods That Return a New Array**

These methods **do not modify** the original array but return a **new array** instead.

## **1.1 `concat()`**

- **Merges** two or more arrays into a new array.

```js
let arr1 = [1, 2];
let arr2 = [3, 4];
let result = arr1.concat(arr2);
console.log(result); // [1, 2, 3, 4]
console.log(arr1); // [1, 2] (unchanged)
```

---

## **1.2 `slice()`**

- **Extracts** a portion of an array without modifying the original.

```js
let arr = [10, 20, 30, 40, 50];
let sliced = arr.slice(1, 4);
console.log(sliced); // [20, 30, 40]
console.log(arr); // [10, 20, 30, 40, 50] (unchanged)
```

---

## **1.3 `filter()`**

- **Returns** a new array with elements that satisfy a condition.

```js
let numbers = [1, 2, 3, 4, 5];
let evens = numbers.filter(num => num % 2 === 0);
console.log(evens); // [2, 4]
```

---

## **1.4 `map()`**

- **Applies** a function to each element and returns a transformed array.

```js

let nums = [1, 2, 3];
let squared = nums.map(n => n * n);
console.log(squared); // [1, 4, 9]
```

---

## **1.5 `flat()`**

- **Flattens** nested arrays into a single array.

```js


let nested = [1, [2, [3, 4]]];
console.log(nested.flat(2)); // [1, 2, 3, 4]
```

---

## **1.6 `flatMap()`**

- **Combines** mapping and flattening in one step.

```js

let words = ["Hello world", "JavaScript"];
let splitWords = words.flatMap(word => word.split(" "));
console.log(splitWords); // ["Hello", "world", "JavaScript"]
```

---

## **1.7 `toSorted()` (ES2023+)**

- **Returns** a sorted copy of the array.

```js

let nums = [3, 1, 4, 2];
console.log(nums.toSorted()); // [1, 2, 3, 4]
```

---

## **1.8 `toReversed()` (ES2023+)**

- **Returns** a reversed copy of the array.

```js
let nums = [1, 2, 3];
console.log(nums.toReversed()); // [3, 2, 1]
```

---

## **1.9 `toSpliced()` (ES2023+)**

- **Returns** a spliced copy without modifying the original.

```js
let arr = [1, 2, 3, 4, 5];
console.log(arr.toSpliced(2, 2)); // [1, 2, 5]
```

---

# **2. Methods That Modify the Original Array**

## **2.1 `push()`** (Add elements to the end)

```js
let arr = [1, 2];
arr.push(3, 4);
console.log(arr); // [1, 2, 3, 4]
```

---

## **2.2 `pop()`** (Remove last element)

```js
let arr = [1, 2, 3];
console.log(arr.pop()); // 3
console.log(arr); // [1, 2]
```

---

## **2.3 `unshift()`** (Add elements to the beginning)

```js
let arr = [2, 3];
arr.unshift(1);
console.log(arr); // [1, 2, 3]
```

---

## **2.4 `shift()`** (Remove first element)

```js
let arr = [1, 2, 3];
console.log(arr.shift()); // 1
console.log(arr); // [2, 3]
```

---

## **2.5 `splice()`** (Modify array elements)

```js
let arr = [1, 2, 3, 4];
arr.splice(1, 2, 9, 10);
console.log(arr); // [1, 9, 10, 4]
```

---

## **2.6 `sort()`** (Sort elements in place)

```js
let arr = [3, 1, 4, 2];
arr.sort();
console.log(arr); // [1, 2, 3, 4]
```

---

## **2.7 `reverse()`** (Reverse elements in place)

```js
let arr = [1, 2, 3];
arr.reverse();
console.log(arr); // [3, 2, 1]
```

---

## **2.8 `fill()`** (Fill elements with a value)

```js
let arr = [1, 2, 3];
arr.fill(0, 1, 3);
console.log(arr); // [1, 0, 0]
```

---

## **2.9 `copyWithin()`** (Copy part of array)

```js
let arr = [1, 2, 3, 4];
arr.copyWithin(1, 2);
console.log(arr); // [1, 3, 4, 4]
```

---

# **3. Methods That Return a Value (Do Not Modify Array)**

## **3.1 `indexOf()`** (Find index of value)

```js
console.log([10, 20, 30].indexOf(20)); // 1
```

---

## **3.2 `lastIndexOf()`**

```js
console.log([10, 20, 30, 20].lastIndexOf(20)); // 3
```

---

## **3.3 `includes()`**

```js
console.log([10, 20, 30].includes(20)); // true
```

---

## **3.4 `find()`**

```js
console.log([1, 2, 3].find(n => n > 1)); // 2
```

---

## **3.5 `findIndex()`**

```js
console.log([1, 2, 3].findIndex(n => n > 1)); // 1
```

---

# **4. Methods That Convert an Array to a String**

## **4.1 `join()`**

```js
console.log([1, 2, 3].join('-')); // "1-2-3"
```

---

## **4.2 `toString()`**

```js
console.log([1, 2, 3].toString()); // "1,2,3"
```

---

This is the **complete** list of JavaScript array methods with explanations and examples. Let me know if you need **further explanations** or **real-world use cases**!