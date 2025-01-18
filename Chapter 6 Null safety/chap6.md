# 🔒 **Null Safety in Kotlin**  
In Kotlin, **`null` values** represent something that is **missing** or **not yet set**. Null safety ensures your code handles these situations gracefully without running into errors like the dreaded **`NullPointerException`**. 🚫⚠️

---

## ✅ **What Does Null Safety Do?**  
Null safety allows you to:  
- Explicitly declare when `null` values are allowed in your program.  
- Check for `null` values.  
- Use **safe calls** to access properties or functions that might contain `null`.  
- Provide default actions for handling `null` values.  

---

# ❓ **Nullable Types**  
By default, variables in Kotlin **cannot be `null`**. However, you can allow `null` values by adding a **`?`** after the type declaration.  

### **Example: Nullable vs Non-Nullable Types 🛠️**  
```kotlin
fun main() {
    var petName: String = "Buddy"  // Non-nullable
    // petName = null  // ❌ Compiler error: Cannot assign null to a non-nullable type

    var favoriteToy: String? = "Chew Toy"  // Nullable
    favoriteToy = null  // ✅ Allowed because of the `?`
}
```
## **🔍 Checking for Null Values**
You can check for the presence of `null` values within conditional expressions
### **Example: Describe a Pet's Name 🐶**
```Kotlin
fun describePetName(name: String?): String {
    return if (name == null) {
        "No name provided 😞"
    } else if (name.isEmpty()) {
        "Pet has an empty name! 🤔"
    } else {
        "Pet's name is $name, and it’s awesome! 🎉"
    }
}

fun main() {
    println(describePetName(null))        // No name provided 😞
    println(describePetName(""))          // Pet has an empty name! 🤔
    println(describePetName("Buddy"))     // Pet's name is Buddy, and it’s awesome! 🎉
}
```

## **🛡️ Using Safe Calls**
To safely access properties of a `null` object, use the safe call operator `?.`.
This operator returns `null` if the object or its properties are `null`, preventing errors.
### **Example: Check the Length of a Toy Name 🎾**
```Kotlin
fun toyLength(toyName: String?): Int? {
    return toyName?.length  // Returns the length or null
}

fun main() {
    val toy: String? = null
    println(toyLength(toy))  // Output: null

    val anotherToy: String? = "Rubber Ball"
    println(toyLength(anotherToy))  // Output: 11
}
```

## **🎭 The Elvis Operator**
You can provide a default value to return if a null value is detected by using the Elvis operator `?:`.
### **Example: Toy Length with a Default Value 🎲**
```Kotlin
fun main() {
    val toy: String? = null
    val length = toy?.length ?: 0  // If toy is null, default to 0
    println("Toy name length: $length")  // Output: Toy name length: 0
}
```