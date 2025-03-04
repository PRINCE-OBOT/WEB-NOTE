
### What is Hardcoding?

Hardcoding means putting fixed values directly into your code instead of using variables or external inputs. This makes the program difficult to change later.

### Example of Hardcoding

Imagine you are writing a program that always calculates a discount of **$10** on a product. If you write:

```js
function getDiscountedPrice(price) {
    return price - 10;  // The discount is always 10
}

console.log(getDiscountedPrice(100)); // 90
console.log(getDiscountedPrice(200)); // 190
```

Here, `10` is **hardcoded**, meaning it cannot be easily changed without editing the code.

### Why is Hardcoding Bad?

If later you want to change the discount to **$15**, you must manually update the code everywhere.

### A Better Way (Avoiding Hardcoding)

Instead of fixing the discount value, use a variable or parameter:

```js
function getDiscountedPrice(price, discount) {
    return price - discount;  
}

console.log(getDiscountedPrice(100, 10)); // 90
console.log(getDiscountedPrice(200, 15)); // 185
```

Now, you can change the discount easily without modifying the code.

Hardcoding makes programs **less flexible** and **harder to update**, so developers try to avoid it.

Does this explanation help?