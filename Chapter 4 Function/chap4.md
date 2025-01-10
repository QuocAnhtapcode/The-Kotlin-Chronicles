# 🛠️ **Functions in Kotlin**  
Sometimes, your `main` block starts looking like a **to-do list on steroids**—long and messy! Functions help break down your code into neat, reusable blocks. ✨  

---

### ✨ **Function Without Parameters**  
A function that performs an action without taking any input.  
```kotlin
fun greet() {
    println("Hello, world! 🌍")
}

fun main() {
    greet()
    // Output: Hello, world! 🌍
}
```

### **✏️ Function With Parameters**
```kotlin
fun sum(x: Int, y: Int): Int {
    return x + y
}

fun main() {
    println(sum(1, 2))
    // 3
}
```

# ⚡**Lambda Expressions**
A lambda expression is like a mini function you can assign to a variable. It allows you to write shorter, more concise code! 💡

### Example 1: Uppercasing a String 🔠
- Here’s a traditional function:
```kotlin
fun uppercaseString(text: String): String {
    return text.uppercase()
}
fun main() {
    println(uppercaseString("hello"))
    // HELLO
}
```
- And here’s the lambda expression version:
```kotlin
fun main() {
    val upperCaseString = { text: String -> text.uppercase() }
    println(upperCaseString("hello"))
    // HELLO
}
```

Lambda expressions can be used in a number of ways. You can:
- 🏗️ Passing a Lambda Expression as a Parameter
```kotlin
val numbers = listOf(1, -2, 3, -4, 5, -6)

val positives = numbers.filter ({ x -> x > 0 })

val isNegative = { x: Int -> x < 0 }
val negatives = numbers.filter(isNegative)

println(positives)
// [1, 3, 5]
println(negatives)
// [-2, -4, -6]
```
- 🔄 Returning a Lambda Expression from a Function
- 🚀 Invoking a Lambda Expression Directly

# 🔧 **Function Types in Kotlin**  
Before you can return a **lambda expression** from a function, you should understand **function types**—which describe the types of parameters a function takes and the type of value it returns.

---

## 📝 **Syntax of a Function Type**  
The syntax for a function type includes:  
- 📦 Each parameter's **type** inside parentheses `()` separated by commas `,`.  
- 🎯 The **return type** written after `->`.  

---

### **Examples of Function Types:**  
- `(String) -> String` – A function that takes a `String` and returns a `String`.  
- `(Int, Int) -> Int` – A function that takes two integers and returns an integer.

```kotlin
val toUpperCase: (String) -> String = { text -> text.uppercase() }

fun main() {
    println(toUpperCase("hello"))
    // Output: HELLO
}
```
### 🚦**Returning a Lambda Expression from a Function**
You can return lambda expressions from functions! The function type helps the compiler understand what type of lambda is being returned.

Example: Time Converter ⏱️
```kotlin
fun toSeconds(time: String): (Int) -> Int = when (time) {
    "hour" -> { value -> value * 60 * 60 }
    "minute" -> { value -> value * 60 }
    "second" -> { value -> value }
    else -> { value -> value }
}

fun main() {
    val timesInMinutes = listOf(2, 10, 15, 1)
    val min2sec = toSeconds("minute")
    val totalTimeInSeconds = timesInMinutes.map(min2sec).sum()
    println("Total time is $totalTimeInSeconds secs")
    // Total time is 1680 secs
}
```
### 🍕** Invoking a Lambda Expression Directly**
You can invoke a lambda expression directly without assigning it to a variable by adding parentheses `()` after the curly braces `{}`.

Example: Pizza Review Time
```kotlin
fun main() {
    ({ food: String -> println("Mmm... $food is delicious! 🍕") })("Pizza")
    // Output: Mmm... Pizza is delicious! 🍕
}
```

# **Trailing lambdas**
If a lambda expression is:
- The only parameter of a function, you can drop the parentheses ().
- The last parameter of a function, you can write it outside the parentheses.

This syntax is called a trailing lambda.

Example: Summing a List with fold()
```kotin
// The operation sums the initial value with every item in the list cumulatively.
println(listOf(1, 2, 3).fold(0, { x, item -> x + item })) // 6

// Alternatively, in the form of a trailing lambda
println(listOf(1, 2, 3).fold(0) { x, item -> x + item })  // 6
```

