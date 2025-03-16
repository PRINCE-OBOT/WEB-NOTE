
### **To Convert Any Base to Decimal**

You need to use `parseInt(string, radix)`, which converts a number **from any base to decimal**.

### **Examples**

```js

console.log(parseInt("10000000", 2)); // 128 (Binary → Decimal)
console.log(parseInt("200", 8));      // 128 (Octal → Decimal)
console.log(parseInt("80", 16));      // 128 (Hex → Decimal)
```

### **Summary**

- **`parseInt(str, base)`** → Converts **any base** to decimal.
