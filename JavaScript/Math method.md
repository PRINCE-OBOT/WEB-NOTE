Here is a **detailed explanation** of all JavaScript `Math` methods, including **code examples**, categorized for easy understanding.

---

## **1. Rounding Methods**

These methods round numbers in different ways.

### `Math.round(x)`

Rounds `x` to the nearest integer.

```js
console.log(Math.round(4.6)); // 5
console.log(Math.round(4.4)); // 4
console.log(Math.round(-4.5)); // -4 (for 5. Negative Round toward 0, meaning it remove the decimal place)
```

### `Math.floor(x)`

Rounds `x` **down** to the nearest integer.

```js
console.log(Math.floor(4.9)); // 4
console.log(Math.floor(-4.1)); // -5
```

### `Math.ceil(x)`

Rounds `x` **up** to the nearest integer.

```js
console.log(Math.ceil(4.1)); // 5
console.log(Math.ceil(-4.9)); // -4
```

### `Math.trunc(x)`

Removes the decimal part of `x`, returning only the integer part.

```js
console.log(Math.trunc(4.9)); // 4
console.log(Math.trunc(-4.9)); // -4
```

---

## **2. Absolute and Power Functions**

These methods handle absolute values, square roots, and exponents.

### `Math.abs(x)`

Returns the absolute (positive) value of `x`.

```js
console.log(Math.abs(-5)); // 5
console.log(Math.abs(5));  // 5
```

### `Math.sqrt(x)`

Returns the **square root** of `x`.

```js
console.log(Math.sqrt(16)); // 4
console.log(Math.sqrt(2));  // 1.414
```

### `Math.cbrt(x)`

Returns the **cube root** of `x`.

```js
console.log(Math.cbrt(27)); // 3
console.log(Math.cbrt(-8)); // -2
```

### `Math.pow(x, y)`

Returns `x` raised to the power of `y` (`x^y`).

```js
console.log(Math.pow(2, 3)); // 8
console.log(Math.pow(5, 2)); // 25
```

### `Math.exp(x)`

Returns `e^x` (Euler's number raised to `x`).

```js
console.log(Math.exp(1)); // 2.718 (approx. value of e)
console.log(Math.exp(2)); // 7.389
```

### `Math.expm1(x)`

Returns `e^x - 1`, useful for small values of `x`.

```js
console.log(Math.expm1(1)); // 1.718
console.log(Math.expm1(0.01)); // 0.010050
```

---

## **3. Logarithmic Methods**

These methods deal with logarithms.

### `Math.log(x)`

Returns the **natural logarithm** (log base `e`).

```js
console.log(Math.log(10)); // 2.302
console.log(Math.log(1));  // 0
```

### `Math.log2(x)`

Returns the logarithm of `x` to base `2`.

```js
console.log(Math.log2(8)); // 3
console.log(Math.log2(16)); // 4
```

### `Math.log10(x)`

Returns the logarithm of `x` to base `10`.

```js
console.log(Math.log10(100)); // 2
console.log(Math.log10(1000)); // 3
```

### `Math.log1p(x)`

Returns `Math.log(1 + x)`, useful for small values of `x`.

```js
console.log(Math.log1p(0.1)); // 0.0953
console.log(Math.log1p(0));   // 0
```

---

## **4. Trigonometric Methods**

These methods deal with angles and radians.

### `Math.sin(x)`

Returns the **sine** of `x` (in radians).

```js
console.log(Math.sin(Math.PI / 2)); // 1
console.log(Math.sin(0)); // 0
```

### `Math.cos(x)`

Returns the **cosine** of `x` (in radians).

```js
console.log(Math.cos(0)); // 1
console.log(Math.cos(Math.PI)); // -1
```

### `Math.tan(x)`

Returns the **tangent** of `x` (in radians).

```js
console.log(Math.tan(Math.PI / 4)); // 1
console.log(Math.tan(0)); // 0
```

### `Math.asin(x)`

Returns the **arcsine** (inverse sine) of `x` in radians.

```js
console.log(Math.asin(1)); // 1.57 (π/2)
console.log(Math.asin(0)); // 0
```

### `Math.acos(x)`

Returns the **arccosine** (inverse cosine) of `x` in radians.

```js
console.log(Math.acos(1)); // 0
console.log(Math.acos(0)); // 1.57 (π/2)
```

### `Math.atan(x)`

Returns the **arctangent** (inverse tangent) of `x` in radians.

```js
console.log(Math.atan(1)); // 0.785 (π/4)
```

### `Math.atan2(y, x)`

Returns the angle between the positive x-axis and the point `(x, y)`.

```js
console.log(Math.atan2(1, 1)); // 0.785 (π/4)
console.log(Math.atan2(0, -1)); // 3.141 (π)
```

---

## **5. Min, Max, and Random Numbers**

### `Math.min(a, b, ...)`

Returns the smallest number.

```js
console.log(Math.min(5, 2, 8, 1)); // 1
```

### `Math.max(a, b, ...)`

Returns the largest number.

```js
console.log(Math.max(5, 2, 8, 1)); // 8
```

### `Math.random()`

Returns a **random** number between `0` and `1`.

```js
console.log(Math.random()); // Example: 0.483920
```

---

## **6. Special Functions**

### `Math.hypot(a, b, ...)`

Returns the square root of the sum of squares.

```js
console.log(Math.hypot(3, 4)); // 5
```

### `Math.sign(x)`

Returns:

- `1` if positive
- `-1` if negative
- `0` if zero

```js
console.log(Math.sign(-5)); // -1
console.log(Math.sign(5));  // 1
console.log(Math.sign(0));  // 0
```

### `Math.fround(x)`

Returns the nearest **32-bit floating-point representation**.

```js
console.log(Math.fround(1.337)); // 1.3370000123977661
```

### `Math.imul(a, b)`

Performs **efficient 32-bit integer multiplication**.

```js
console.log(Math.imul(2, 3)); // 6
```

### `Math.clz32(x)`

Returns the **number of leading zeros** in a 32-bit binary number.

```js
console.log(Math.clz32(1)); // 31
console.log(Math.clz32(16)); // 27
```

---

## **7. Mathematical Constants**

```js
console.log(Math.PI); // 3.141592653589793
console.log(Math.E);  // 2.718281828459045
```

---

This is the **complete guide** to JavaScript `Math` methods with explanations and code examples. Let me know if you need further clarification!