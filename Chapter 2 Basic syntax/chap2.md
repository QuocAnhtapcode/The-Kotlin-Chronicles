# 🌟 Hello, Kotlin World!  
Your first step into Kotlin is as simple as printing a friendly message!  

```kotlin
// Entry point of the program
fun main() {
    println("Hello, world! 🌍")  // Prints "Hello, world!" to the console
}
```

# 📝 Variables in Kotlin
Kotlin has two main types of variables:

- 🔒 Read-only variables `val` – Like a constant; once assigned, it can't be changed.
- 🔄 Mutable variables `var` – A variable that can be updated after initialization.

Think of it this way:
```kotlin
val past = 2.8   // "The past is set in stone."
var future = 2.8  // "The future? That's up to you!"
future = 3.6  // Changing the future is totally allowed.
println("My GPA is $future 🌟")  // Output: My GPA is 3.6
```
`Note`: val helps you write safer code by preventing unwanted changes to important values.

# 🪄 String Templates
Tired of using endless `+` symbols to stitch variables into strings? Say hello to `String Templates`—Kotlin’s magical way of embedding variables directly inside your strings!
```kotlin
println("My current GPA is $past, but next year, my GPA will go up to ${past+0.8}! 🚀")
```
`$past` inserts the value of the past variable.

`${expression}` allows you to include more complex expressions

String templates make your code cleaner and more expressive! 🧙‍♂️✨

# 🧠 **Kotlin Data Types**  
Every variable and data structure in Kotlin has a **type**. Types are important because they tell the compiler what operations can be performed on that variable or data structure.  

---

### 📝 **Type Inference**  
Kotlin has an awesome feature called **type inference** – this means Kotlin can figure out the type of a variable based on the value you assign to it! You don’t always have to explicitly state the type.  

```kotlin
val gpa = 2.8  // Kotlin infers that gpa is a Double
gpa *= 2  // ❌ Error: 'val' cannot be reassigned (immutable variable)
gpa -= 2  // ❌ Error again!
println(gpa)  // Won't even compile due to errors above!
```
### **🗂️ Kotlin Basic Data Types**

| Category | Basic types | Example |
|:---------|:---------|:---------|
| Integers | `Byte` , `Short` , `Int` , `Long` | val year = 2025 |
| Unsigned integers | `UByte` , `UShort` , `UInt` , `ULong` | val score: age = 22 |
| Floating-point numbers | `Float` , `Double` | val gpa = 3.6 |
| Booleans | `Boolean` | val isOld: Boolean = false |
| Characters | `Char` | val c: Char = 'C' |
| Strings | `String` | val message: String = "Hello, world!"

### 🔎 Declaring a Variable Without Initializing It
If you want to declare a variable without assigning a value immediately, you need to specify its type explicitly using `:`. This makes sure Kotlin knows what kind of data it’s expecting.
```kotlin
val gpa: Double  // Declared as a Double, but no value assigned yet
gpa = 3.6  // Now assigning a value to it
println("My final GPA is $gpa 🎓")  // Output: My final GPA is 3.6 🎓
```

# 🗂️ **Collections in Kotlin**  
When programming, it’s useful to group data into structures for easier processing—just like grouping your snacks into categories for a party! 🍕🍟🥤  

Kotlin provides **collections** for exactly this purpose.  

| 🛠️ **Collection Type** | 📝 **Description**                                |
|:-----------------------|:-------------------------------------------------|
| **Lists**              | Ordered collections of items (like a playlist 🎶) |
| **Sets**               | Unique, unordered collections of items (like trading cards 🃏) |
| **Maps**               | Sets of key-value pairs where keys are unique and map to one value (like a dictionary 📖) |

---

### **Immutable vs Mutable Collections**  
Each collection type can either be:  
- **Read-only (immutable)**: Cannot be changed after creation.
- **Mutable**: Can be modified (items can be added, removed, etc.).

---

# 📋 **Lists**  
A **list** stores items in the order that they are added and allows **duplicate items** (think of it as a queue of people waiting for concert tickets 🎫).  

- To create a **read-only list** `List` , use the `listOf()` function.  
- To create a **mutable list** `MutableList` , use the `mutableListOf()` function.

---

### **Examples**  

```kotlin
// Read-only list (Immutable)
val breakfastMenu = listOf("🍳 Eggs", "🥓 Bacon", "🥯 Bagel")
println(breakfastMenu)
// Output: [🍳 Eggs, 🥓 Bacon, 🥯 Bagel]

// Mutable list (can be modified)
val shoppingCart: MutableList<String> = mutableListOf("🍩 Donut", "🍕 Pizza")
shoppingCart.add("🍦 Ice Cream")  // Adding to the list
shoppingCart.remove("🍕 Pizza")  // Removing an item
println(shoppingCart)
// Output: [🍩 Donut, 🍦 Ice Cream]
```

### 🛠️ **Useful Functions for Lists**
1. `add()` – Add an Item
2. `remove()` – Remove an Item
3. `get()` – Access an Item by Index
4. `set()` – Modify an Item
5. `size` – Get the Number of Items
6. `contains()` – Check if an Item Exists
7. `isEmpty()` – Check if the List is Empty
8. `forEach()` – Loop Through the List
9. `indexOf()` – Find the Index of an Item
10. `clear()` – Remove All Items from the List

# 🍇 **Set** in Kotlin  
Unlike **lists**, which are ordered and allow duplicates, **sets** are **unordered** collections that store only **unique** items. Think of a **set** as your collection of trading cards—no duplicates allowed! 🃏

---

## 📝 **How to Create Sets**  
- To create a **read-only set** `Set` , use the `setOf()` function.
- To create a **mutable set** `MutableSet` , use the `mutableSetOf()` function.

---

### **Examples:**  

```kotlin
// Read-only set (Immutable)
val fruitBasket = setOf("🍎 Apple", "🍌 Banana", "🍒 Cherry", "🍒 Cherry")  // Duplicate "🍒 Cherry" will be ignored
println(fruitBasket)
// Output: [🍎 Apple, 🍌 Banana, 🍒 Cherry]

// Mutable set (can be modified)
val dessertSet: MutableSet<String> = mutableSetOf("🍦 Ice Cream", "🍩 Donut", "🍪 Cookie")
dessertSet.add("🍫 Chocolate")  // Adding an item
dessertSet.remove("🍩 Donut")  // Removing an item
println(dessertSet)
// Output: [🍦 Ice Cream, 🍪 Cookie, 🍫 Chocolate]
```

### **🛠️ Useful Functions for Sets**
1. `add()` – Add an Item
2. `remove()` – Remove an Item
3. `contains()` – Check if an Item Exists
4. `size` – Get the Number of Items
5. `isEmpty()` – Check if the Set is Empty
6. `forEach()` – Loop Through the Set
7. `union()` – Combine Two Sets
```kotlin
val set1 = setOf("🍕 Pizza", "🍔 Burger")
val set2 = setOf("🍔 Burger", "🌮 Taco")
val combinedSet = set1.union(set2)
println(combinedSet)
// Output: [🍕 Pizza, 🍔 Burger, 🌮 Taco]
```
8. `intersect()` – Find Common Items Between Sets
```kotlin
val commonItems = set1.intersect(set2)
println(commonItems)
// Output: [🍔 Burger]
```
9. `subtract()` – Find Unique Items in a Set
```kotlin
val uniqueItems = set1.subtract(set2)
println(uniqueItems)
// Output: [🍕 Pizza]
```
10. `clear()` – Remove All Items from the Set

# 🗺️ **Map** in Kotlin  
A **map** is a collection of **key-value pairs** where each key is unique and maps to exactly **one value**—just like a dictionary or a phonebook! 📖  

In Kotlin, **keys** must be unique, but **values** can be duplicated.

---

## 📝 **How to Create Maps**  
- To create a **read-only map** `Map` , use the `mapOf()` function.
- To create a **mutable map** `MutableMap` , use the `mutableMapOf()` function.

---

### **Examples:**  

```kotlin
// Read-only map (Immutable)
val favoriteFoods = mapOf(
    "Alice" to "🍕 Pizza",
    "Bob" to "🍔 Burger",
    "Charlie" to "🌮 Tacos"
)
println(favoriteFoods)
// Output: {Alice=🍕 Pizza, Bob=🍔 Burger, Charlie=🌮 Tacos}

// Mutable map (can be modified)
val studentGrades: MutableMap<String, String> = mutableMapOf(
    "Anna" to "A",
    "Ben" to "B",
    "Chris" to "A"
)
studentGrades["Diana"] = "A+"  // Adding a new key-value pair
studentGrades["Ben"] = "A-"    // Updating an existing value
println(studentGrades)
// Output: {Anna=A, Ben=A-, Chris=A, Diana=A+}
```
### **🛠️ Useful Functions for Maps**
1. `put()` – Add or Update an Entry
2. `remove()` – Remove an Entry by Key
3. `get()` – Retrieve a Value by Key
4. `containsKey()` – Check if a Key Exists
5. `containsValue()` – Check if a Value Exists
6. `keys` – Get All Keys
7. `values` – Get All Values
8. `entries` – Get All Key-Value Pairs
```kotlin
val gradeEntries = studentGrades.entries
gradeEntries.forEach { entry ->
    println("${entry.key} is ${entry.value}")
}
```
9. `isEmpty()` – Check if the Map is Empty
10. `clear()` – Remove All Entries