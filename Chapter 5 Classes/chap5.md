# 🏠 **Classes in Kotlin**  
Kotlin supports **object-oriented programming** with classes and objects. Objects are incredibly useful for organizing and storing data in your program—think of them as blueprints for creating items in your app. 🛠️

---

## 📦 **Declaring a Class**  
To declare a class, use the `class` keyword:  
```kotlin
class Dog
```
This creates a simple class named `Dog`—ready for your app to have its own virtual puppy! 🐶

## 🏷️ **Properties**
Properties are the characteristics or attributes of a class. For example, a `Dog` might have properties like `name` and `breed`.

**Declaring Properties**
```kotlin
class Dog(val name: String, var breed: String)
// or with default values
class Dog(val name: String, var breed: String = "Mixed Breed") {
    val category: String = "Pet"
}
```

## **🛠️ Creating an Instance**
When you create an object (instance) of a class, Kotlin automatically generates a constructor based on the properties in the class header.
```kotlin
class Dog(val name: String, var breed: String)

fun main() {
    val myDog = Dog("Buddy", "Golden Retriever")  // Creating an instance
    println("I just adopted a dog named ${myDog.name}! 🐕")
}
```
## **📥 Accessing Properties**
To access or modify a property of a class instance, use a period `.` after the instance name:
```kotlin
class Dog(val name: String, var breed: String)

fun main() {
    val myDog = Dog("Buddy", "Golden Retriever")
    println("${myDog.name} is a ${myDog.breed}.")  // Access property

    myDog.breed = "Labrador"  // Modify property
    println("${myDog.name} is now a ${myDog.breed}.")
}
```
## **✨ Member Functions**
Member functions are actions or behaviors that a class can perform. They must be declared within the class body. 
To call a member function on an instance, write the function name after the instance name with a `.`
```kotlin
class Dog(val name: String, var breed: String) {
    fun bark() {
        println("Woof! Woof! 🐾 My name is $name!")
    }
}
fun main() {
    val myDog = Dog("Buddy", "Golden Retriever")
    myDog.bark()
    // Output: Woof! Woof! 🐾 My name is Buddy!
}
```
# **🗂️ Data Classes**
Kotlin provides data classes specifically for storing data. They come with built-in functionality like `toString()`, `equals()`, and `copy()`.
To declare a data class, use `data class` :
```kotlin
data class User(val name: String, val id: Int)
```
Data classes have the same functionality as classes, but they come automatically with additional member functions.
## **📋 toString()**
The `toString()` function creates a readable string representation of the object and its properties, which is handy for debugging:
```kotlin
val user = User("Alice", 101)
println(user)
// Output: User(name=Alice, id=101)
```

## **🔍 equals() or ==**
The `equals()` function or `==` operator compares the contents of two objects, not their memory locations.
```kotlin
val user1 = User("Alice", 101)
val user2 = User("Alice", 101)
val user3 = User("Bob", 102)

println(user1 == user2)  // true
println(user1 == user3)  // false
```
## **📑 copy()**
The `copy()` function allows you to clone an object and optionally modify some properties:
```kotlin
val user1 = User("Alice", 101)
val user2 = user1.copy()  // Copy without changes
val user3 = user1.copy(name = "Bob")  // Copy with a modified property

println(user1)  // User(name=Alice, id=101)
println(user2)  // User(name=Alice, id=101)
println(user3)  // User(name=Bob, id=101)
```
