Here’s a comprehensive list of JavaScript string methods, categorized for better understanding, along with explanations and examples.

---

## **1. String Creation**

### **`String()`**

Creates a new string.

```js
let str = String(123); // "123"
let str2 = new String("Hello"); // String object
```

---

## **2. String Length**

### **`.length`**

Returns the length of a string.

```js
let text = "Hello, World!";
console.log(text.length); // 13
```

---

## **3. String Searching Methods**

### **`.indexOf(searchValue, startPosition)`**

Returns the first index of the specified value, or `-1` if not found.

```js
let str = "Hello, World!";
console.log(str.indexOf("World")); // 7
console.log(str.indexOf("o", 5)); // 8
```

### **`.lastIndexOf(searchValue, startPosition)`**

Returns the last occurrence of a value.

```js
console.log(str.lastIndexOf("o")); // 8
```

### **`.includes(searchString, position)`**

Checks if a string contains a specified value, returns `true` or `false`.

```js
console.log(str.includes("World")); // true
console.log(str.includes("world")); // false (case-sensitive)
```

### **`.startsWith(searchString, position)`**

Checks if a string starts with a given substring.

```js
console.log(str.startsWith("Hello")); // true
```

### **`.endsWith(searchString, length)`**

Checks if a string ends with a given substring.

```js
console.log(str.endsWith("!")); // true
```

---

## **4. String Extraction Methods**

### **`.slice(startIndex, endIndex)`**

Extracts part of a string.

```js
console.log(str.slice(0, 5)); // "Hello"
console.log(str.slice(-6, -1)); // "World"
```

### **`.substring(startIndex, endIndex)`**

Similar to `slice()`, but `startIndex` can be greater than `endIndex`.

```js
console.log(str.substring(7, 12)); // "World"
console.log(str.substring(12, 7)); // "World"
```

### **`.substr(startIndex, length)`**

Extracts a substring of specified length.

```js
console.log(str.substr(7, 5)); // "World"
```

---

## **5. String Modification Methods**

### **`.toUpperCase()`**

Converts a string to uppercase.

```js
console.log(str.toUpperCase()); // "HELLO, WORLD!"
```

### **`.toLowerCase()`**

Converts a string to lowercase.

```js
console.log(str.toLowerCase()); // "hello, world!"
```

### **`.trim()`**

Removes whitespace from both ends.

```js
let str2 = "   Hello   ";
console.log(str2.trim()); // "Hello"
```

### **`.trimStart()` / `.trimEnd()`**

Removes whitespace from the start or end.

```js
console.log(str2.trimStart()); // "Hello   "
console.log(str2.trimEnd()); // "   Hello"
```

### **`.padStart(targetLength, padString)`**

Pads the start of a string.

```js
console.log("5".padStart(3, "0")); // "005"
```

### **`.padEnd(targetLength, padString)`**

Pads the end of a string.

```js
console.log("5".padEnd(3, "0")); // "500"
```

---

## **6. String Replacement Methods**

### **`.replace(searchValue, newValue)`**

Replaces the first occurrence of a value.

```js
console.log("Hello World".replace("World", "JS")); // "Hello JS"
```

### **`.replaceAll(searchValue, newValue)`**

Replaces all occurrences of a value.

```js
console.log("abc abc abc".replaceAll("abc", "xyz")); // "xyz xyz xyz"
```

---

## **7. String Splitting Method**

### **`.split(separator, limit)`**

Splits a string into an array.

```js
console.log("a,b,c".split(",")); // ["a", "b", "c"]
console.log("hello".split("")); // ["h", "e", "l", "l", "o"]
```

---

## **8. String Concatenation**

### **`.concat(string1, string2, ...)`**

Joins multiple strings.

```js
console.log("Hello".concat(", ", "World!")); // "Hello, World!"
```

---

## **9. String Character Access Methods**

### **`.charAt(index)`**

Returns a character at a given index.

```js
console.log("Hello".charAt(1)); // "e"
```

### **`.charCodeAt(index)`**

Returns the Unicode of a character.

```js
console.log("ABC".charCodeAt(0)); // 65
```

### **`.codePointAt(index)`**

Returns the Unicode of a character (for extended Unicode).

```js
console.log("𝌆".codePointAt(0)); // 119558
```

### **`.at(index)`** _(ES2022)_

Allows negative indexing.

```js
console.log("Hello".at(-1)); // "o"
```

---

## **10. String Conversion Methods**

### **`.toString()`**

Converts a value to a string.

```js
let num = 123;
console.log(num.toString()); // "123"
```

---

## **11. String Comparison**

### **`.localeCompare(compareString)`**

Compares two strings lexicographically.

```js
console.log("apple".localeCompare("banana")); // -1 (apple comes first)
```

---

## **12. String Iteration**

### **`.repeat(count)`**

Repeats a string multiple times.

```js
console.log("Hi!".repeat(3)); // "Hi!Hi!Hi!"
```

---

## **13. Template Literals (Backticks )**

Supports multi-line strings and expressions.

```js
let name = "John";
console.log(`Hello, ${name}!`); // "Hello, John!"
```

---

This covers all major JavaScript string methods with examples. Let me know if you need further clarification!