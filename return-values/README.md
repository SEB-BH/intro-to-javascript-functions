<h1>
  <span class="headline">Intro to JavaScript Functions</span>
  <span class="subhead">Return Values</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to return data from functions using the `return` statement.

## Returning values from a function

So far, we've used `console.log()` inside our functions to display results in the console.

But what if we want to **use the result somewhere else in our code?**

This is where the **`return` keyword** comes in.

The `return` keyword allows a function to send a value back to the place where it was called.

Let's update our `add()` function to use `return` instead of `console.log()`:

```javascript
function add(numA, numB) {
  return numA + numB
}
```

Now, let's call our function:

```javascript
add(1, 5)
```

When JavaScript runs this code:

1. It goes to our `add()` function.
2. It replaces `numA` with `1` and `numB` with `5`.
3. It calculates `1 + 5`.
4. The `return` statement **sends the answer (`6`) back to the place where we called the function**.

Think of it this way:

```javascript
add(1, 5) // This gives us the value 6
```

But there's something important to understand: **returning a value does not automatically print it in the terminal.**

If we want to see the answer in our terminal, we need to use `console.log()`:

```javascript
console.log(add(1, 5)) // 6
```

Here's what happens:

1. JavaScript runs `add(1, 5)` first.
2. The function returns `6`.
3. `console.log()` prints that `6` in our terminal.

So you can think of this:

```javascript
console.log(add(1, 5))
```

As working like this:

```javascript
console.log(6)
```

> 💡 **Remember:** `return` gives us a value we can use in our code. `console.log()` simply lets us see that value in the terminal.

Let's look at what happens when we use `console.log()` instead of `return` inside of our function:

```javascript
function add(numA, numB) {
  console.log(numA + numB)
}

const result = add(2, 3)

console.log(result)
```

**Console output:**

```text
5
undefined
```

Why do we see `undefined`?

The function logs `5` to the console, but it doesn't actually return a value.

When a function doesn't explicitly return a value, JavaScript automatically returns `undefined`.

> 💡 **Remember:** Logging a value is not the same as returning it!

### Using returned values

One of the biggest benefits of `return` is that we can store the result of a function in a variable.

Let's use our updated `add()` function:

```javascript
function add(numA, numB) {
  return numA + numB
}

const result = add(1, 5)

console.log(result) // 6
```

We can also use that returned value in another calculation:

```javascript
const result = add(1, 5)

console.log(result * 2) // 12
```

Because our function returns a number, we can use that number just like any other number in JavaScript.

### `return` stops a function

Another important thing to know is that **when JavaScript reaches a `return` statement, the function immediately stops running.**

For example:

```javascript
function greet(name) {
  return `Hello, ${name}!`

  console.log("This will never run")
}

console.log(greet("Sara")) // Hello, Sara!
```

The `console.log()` inside the function never runs because it comes after the `return` statement.

> 💡 Any code after an executed `return` statement will not run.

### Returning values with conditionals

We can also use `return` inside an `if` statement to return different values depending on a condition.

For example:

```javascript
function checkAge(age) {
  if (age >= 18) {
    return "Adult"
  } else {
    return "Minor"
  }
}

console.log(checkAge(25)) // Adult
console.log(checkAge(15)) // Minor
```

This function has two `return` statements, but only one will run each time we call the function.

- If the age is 18 or older, the function returns `"Adult"`.
- Otherwise, the function returns `"Minor"`.

Because `return` stops the function, we can also write this without `else`:

```javascript
function checkAge(age) {
  if (age >= 18) {
    return "Adult"
  }

  return "Minor"
}
```

Both versions work the same way!

### 🎓 You Do

**Part 1: Returning a calculation**

Create a function called `multiply()` that:

1. Accepts two numbers as parameters.
2. Multiplies the two numbers.
3. Returns the result.

Call the function, store the returned value in a variable, and log that variable to the console.

**Expected result:**

```javascript
const answer = multiply(4, 5)

console.log(answer) // 20
```

**Part 2: Returning a value based on a condition**

Create a function called `hasPassed()` that:

1. Accepts a student's score as a parameter.
2. Returns `true` if the score is 70 or higher.
3. Returns `false` if the score is below 70.

**Expected results:**

```javascript
console.log(hasPassed(85)) // true
console.log(hasPassed(45)) // false
console.log(hasPassed(70)) // true
```

> 🧠 **Good habit:** Use `return` when you want your function to provide a result that other parts of your code can use. Use `console.log()` when you want to check or display values in the console while testing your code.
