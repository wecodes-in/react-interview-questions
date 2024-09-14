# React Interview Questions & Answers

> Click :star: if you find this helpful! Contributions are welcome. Follow us [@wecodes_in](https://medium.com/@gajendra.gangwar/) for technical updates and insights.

---

**Note:** This repository focuses on ReactJS Advance Questions.

### Table of Contents

<details open>
<summary>
Hide/Show table of contents
</summary>

- [JavaScript Call by Value and Call by Reference Interview Questions](#javascript-call-by-value-and-call-by-reference-interview-questions)
- [React Interview Questions](#react-interview-questions)

</details>


---

## JavaScript Call by Value and Call by Reference Interview Questions

1. **Explain the difference between call by value and call by reference in JavaScript. Can you give an example of each?**

2. **If JavaScript is said to use "call by value" for both primitive and reference types, why do objects behave as though they are passed by reference?**

3. **What would happen if you reassign an object parameter inside a function?**

4. **Can you simulate pass by reference behavior for primitive types in JavaScript?**

5. **What happens if you try to modify an object property inside a function but also reassign it? What’s the difference in behavior between modifying the property and reassigning the object?**

6. **In JavaScript, are arrays passed by value or by reference? How can you prove it?**

7. **How would you prevent an object from being modified inside a function, despite JavaScript's call by reference behavior?**

8. **How does the spread operator (`...`) behave in terms of call by value and reference?**

9. **Does JavaScript support true pass by reference, where the variable's reference can be changed from inside the function?**

10. **How does JavaScript handle the immutability of primitive data types when passed into functions?**

---

## React Interview Questions


## JavaScript Call by Value and Call by Reference Interview Questions

1. **Explain the difference between call by value and call by reference in JavaScript. Can you give an example of each?**

   - **Answer:** 
     - **Call by value**: JavaScript passes primitive data types (like numbers, strings, booleans) by value. This means a copy of the value is passed to the function, so changes inside the function do not affect the original variable.
     - **Call by reference**: JavaScript passes reference types (like objects and arrays) by reference. This means the reference to the object or array is passed, so changes inside the function affect the original object or array.

   - **Example:**

     ```js
     // Call by value
     let num = 10;

     function changeValue(x) {
       x = 20;
     }

     changeValue(num);
     console.log(num);  // Output: 10
     ```

     ```js
     // Call by reference
     let obj = { name: "Alice" };

     function modifyObject(o) {
       o.name = "Bob";
     }

     modifyObject(obj);
     console.log(obj);  // Output: { name: "Bob" }
     ```

2. **If JavaScript is said to use "call by value" for both primitive and reference types, why do objects behave as though they are passed by reference?**

   - **Answer:** 
     JavaScript uses call by value for both primitive and reference types. For reference types, the value being passed is a reference to the object, not the actual object itself. This reference is copied, so while you can't change the reference itself, you can modify the object it points to.

3. **What would happen if you reassign an object parameter inside a function?**

   - **Answer:** 
     Reassigning an object parameter inside a function only changes the local reference, not the original reference outside the function. The original object remains unchanged.

   - **Example:**

     ```js
     let obj = { name: "Alice" };

     function modifyObject(o) {
       o = { name: "Bob" };  // Reassigns the local reference
     }

     modifyObject(obj);
     console.log(obj);  // Output: { name: "Alice" }
     ```

4. **Can you simulate pass by reference behavior for primitive types in JavaScript?**

   - **Answer:** 
     You can't directly simulate pass by reference for primitive types, but you can wrap primitives in an object or array to indirectly modify their value.

   - **Example:**

     ```js
     let value = { num: 5 };

     function modifyPrimitive(val) {
       val.num = 10;
     }

     modifyPrimitive(value);
     console.log(value.num);  // Output: 10
     ```

5. **What happens if you try to modify an object property inside a function but also reassign it? What’s the difference in behavior between modifying the property and reassigning the object?**

   - **Answer:** 
     Modifying an object's property inside a function will affect the original object because the reference to the object is passed. Reassigning the object inside the function only changes the local reference and does not affect the original object.

   - **Example:**

     ```js
     let obj = { name: "Alice", details: { age: 25 } };

     function modifyObject(o) {
       o.name = "Bob";  // Modifies the original object
       o = { name: "Charlie" };  // Reassigns, does not affect the original reference
     }

     modifyObject(obj);
     console.log(obj);  // Output: { name: "Bob", details: { age: 25 } }
     ```

6. **In JavaScript, are arrays passed by value or by reference? How can you prove it?**

   - **Answer:** 
     Arrays are passed by reference. This means modifications to the array inside the function affect the original array.

   - **Example:**

     ```js
     let arr = [1, 2, 3];

     function modifyArray(a) {
       a[0] = 10;  // Modifies the original array
     }

     modifyArray(arr);
     console.log(arr);  // Output: [10, 2, 3]
     ```

7. **How would you prevent an object from being modified inside a function, despite JavaScript's call by reference behavior?**

   - **Answer:** 
     Use `Object.freeze()` to make an object immutable or create a shallow copy of the object using `Object.assign()` or the spread operator.

   - **Example:**

     ```js
     let obj = { name: "Alice" };

     Object.freeze(obj);

     function modifyObject(o) {
       o.name = "Bob";  // No effect, as obj is frozen
     }

     modifyObject(obj);
     console.log(obj);  // Output: { name: "Alice" }
     ```

8. **How does the spread operator (`...`) behave in terms of call by value and reference?**

   - **Answer:** 
     The spread operator creates a shallow copy of an object or array. It copies the top level but not nested objects. Therefore, nested objects are still passed by reference.

   - **Example:**

     ```js
     let obj = { name: "Alice", details: { age: 25 } };
     let copy = { ...obj };

     copy.name = "Bob";
     console.log(obj.name);  // Output: Alice

     copy.details.age = 30;
     console.log(obj.details.age);  // Output: 30
     ```

9. **Does JavaScript support true pass by reference, where the variable's reference can be changed from inside the function?**

   - **Answer:** 
     No, JavaScript does not support true pass by reference. You can modify the contents of an object or array, but you cannot change the reference itself to point to a different object or array from within the function.

10. **How does JavaScript handle the immutability of primitive data types when passed into functions?**

    - **Answer:** 
      Primitive data types are immutable. When passed into functions, JavaScript copies the value, and any changes to this copy do not affect the original variable.

    - **Example:**

      ```js
      let str = "Hello";

      function changeString(s) {
        s = "World";  // Changes the local copy, not the original
      }

      changeString(str);
      console.log(str);  // Output: Hello
      ```

---

## React Interview Questions

