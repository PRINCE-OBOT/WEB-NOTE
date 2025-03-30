

## **1. `toggle(className)`**

### **Basic Behavior (Without Callback)**

```js
element.classList.toggle('hidden');
```

- If the element **has** the class → it **removes** it.
- If the element **does not have** the class → it **adds** it.
- Works like a **switch** (on/off behavior).

### **With Callback (Condition)**

```js
element.classList.toggle('hidden', condition);
```

- If `condition` is **true** → **adds** the class.
- If `condition` is **false** → **removes** the class.
- Instead of toggling, it **forces** the class to be in sync with the condition.

### **Example**

```js
const box = document.querySelector('.box');
box.classList.toggle('hidden', box.textContent.includes('hide'));
```

- If `box.textContent` includes `"hide"`, it **adds** `hidden`.
- Otherwise, it **removes** `hidden`.

---

## **2. `add(className)`**

```js
element.classList.add('hidden');
```

- Always **adds** the class if it's not there.
- Does **nothing** if the class is already present.

### **With Callback**

Unlike `toggle()`, `add()` doesn’t accept a callback function directly. Instead, you must handle conditions manually:

```js
if (box.textContent.includes('hide')) {
  box.classList.add('hidden');
}
```

This ensures the class is always added **when the condition is met**.

---

## **3. `remove(className)`**

```js
element.classList.remove('hidden');
```

- Always **removes** the class if it's there.
- Does **nothing** if the class isn’t present.

### **With Callback**

Again, `remove()` doesn’t take a callback, so you must handle conditions manually:

```js
if (!box.textContent.includes('hide')) {
  box.classList.remove('hidden');
}
```

This ensures the class is removed **when the condition is met**.

---

Aside from `toggle()`, `add()`, and `remove()`, the `classList` API provides other useful methods for managing CSS classes in JavaScript:



# 4. **`contains(className)`**
    
- Checks if an element has a specific class.

- Returns `true` if the class exists, otherwise `false`.
    
    ```js
    
if (element.classList.contains('hidden')) {
        console.log('Element is hidden');
    }
    ```
    


# 5. **`replace(oldClass, newClass)`**
    

- Replaces an existing class with a new one.
    
- If `oldClass` doesn’t exist, nothing happens.
    
    ```js
    element.classList.replace('old-class', 'new-class');
    ```
    
# 6. **`item(index)`**
    

- Retrieves the class at a specific index (like an array).
    
- Returns `null` if the index is out of bounds.
    
    ```js
    console.log(element.classList.item(0)); // Logs the first class
    ```
    
# 7. **`length` (Property, not a method)**
    
- Returns the number of classes on the element.
    
    ```js
    console.log(element.classList.length); // Number of classes
    ```
    
# 8. **`forEach(callback)`**
    
    
- Iterates over all classes applied to an element.
    
    ```js
    element.classList.forEach(cls => {
        console.log(cls);
    });
    ```
    
