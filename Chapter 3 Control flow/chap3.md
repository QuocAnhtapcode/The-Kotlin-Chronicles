# 🤔 **Conditional Expressions in Kotlin**  
Kotlin provides **`if`** and **`when`** statements for checking conditions. Let’s dive into the world of Kotlin's decision-making, where your code can choose its destiny—just like you decide between coffee ☕ and tea 🍵 every morning!

---

## ✨ **`if` Statements**  
The `if` statement works like a gatekeeper—if the condition is `true`, it lets the action happen. If `false`, it sends you to the `else` block.

---

### **Example: Dice Game 🎲**  
```kotlin
val number = randomInt(3,18);
if(number>=3 && number<=10){
    println("Xỉu");
}else{
    println("Tài);
}
```
## **🛡️ `when` Statements**
The `when` statement is Kotlin's way of handling multiple conditions—like a buffet table where you choose different actions based on what’s available! 🍕🍟🌭
### **Example 1: Breakfast Decision 🥐**
```kotlin
val breakfastOrder = "Coffee"

when (breakfastOrder) {
    "Coffee" -> println("☕ Your day is powered by caffeine!")
    "Pancakes" -> println("🥞 Sweet and fluffy happiness!")
    "Toast" -> println("🍞 Simple and comforting!")
    else -> println("🥣 Surprise breakfast time!")
}
// Output: ☕ Your day is powered by caffeine!
```

Note that all branch conditions are checked sequentially until one of them is satisfied. So only the first suitable branch is executed.

### **Example 2: Hogwarts Sorting Hat 🧙‍♂️**
```kotlin
val studentName = "Harry"

val house = when (studentName) {
    "Harry" -> "Gryffindor 🦁"
    "Draco" -> "Slytherin 🐍"
    "Luna" -> "Ravenclaw 🦅"
    "Cedric" -> "Hufflepuff 🦡"
    else -> "Muggle 🧍"
}
println("$studentName belongs to $house")
// Output: Harry belongs to Gryffindor 🦁
```

### **Example 3: Traffic Light Simulator 🚦**
```kotlin
fun main() {
val trafficLightState = listOf("Green", "Yellow", "Red").random()  // Random traffic light state

val trafficAction = when (trafficLightState) {
    "Green" -> "🚗 Go!"
    "Yellow" -> "⚠️ Slow down!"
    "Red" -> "🛑 Stop!"
    else -> "🚦 Malfunction! Proceed with caution!"
}
println("The traffic light is $trafficLightState: $trafficAction")
// Possible Output: The traffic light is Red: 🛑 Stop!

}
```

# Ranges
Before talking about loops, it's useful to know how to construct ranges for loops to iterate over.

The most common way to create a range in Kotlin is to use the `..` operator. For example, `1..4` is equivalent to `1, 2, 3, 4`.

To declare a range that doesn't include the end value, use the `..<` operator. For example, `1..<4` is equivalent to `1, 2, 3`.

To declare a range in reverse order, use `downTo`. For example, `4 downTo 1` is equivalent to `4, 3, 2, 1`.

To declare a range that increments in a step that isn't 1, use `step `and your desired increment value. For example, `1..5 step 2` is equivalent to `1, 3, 5`.

You can also do the same with `Char` ranges:

`'a'..'d'` is equivalent to `'a', 'b', 'c', 'd'`

`'z' downTo 's' step 2` is equivalent to `'z', 'x', 'v', 't'`

# 🔄 **Loops in Kotlin**  
Loops are like playlists on repeat—they let your program perform the same action multiple times until it’s time to stop. The two most common types of loops are `for` and `while`.

- Use **`for` loops** when you know how many times you want to iterate.  
- Use **`while` loops** when you want to keep doing something until a condition is met.

---

## 🎢 **For Loops**  
The `for` loop iterates over a range of values, performing an action for each value—like riding a roller coaster from start to finish! 🎠

---

### **Example 1: Countdown to Launch 🚀**  
```kotlin
for (count in 5 downTo 1) {
    println("$count...")
}
println("Liftoff! 🚀")
// Output:
// 5...
// 4...
// 3...
// 2...
// 1...
// Liftoff! 🚀
```
### **Example 2: Snacks on the Table 🍩**
```kotlin
val snacks = listOf("🍩 Donut", "🍕 Pizza", "🍦 Ice Cream")

for (snack in snacks) {
    println("I can't resist a $snack!")
}
// Output:
// I can't resist a 🍩 Donut!
// I can't resist a 🍕 Pizza!
// I can't resist a 🍦 Ice Cream!
```

# ⏳ **While Loops**
The `while` loop checks a condition **before** executing the code block. If the condition is true, it repeats the block until the condition becomes false—just like eating cookies until the jar is empty! 🍪

### **Example: Balloon Inflation 🎈**
```kotlin
var balloonSize = 0

while (balloonSize < 10) {
    println("🎈 Balloon is inflating! Size: $balloonSize")
    balloonSize++
}
println("🎉 The balloon is fully inflated!")
// Output:
// 🎈 Balloon is inflating! Size: 0
// ...
// 🎈 Balloon is inflating! Size: 9
// 🎉 The balloon is fully inflated!
```

# 🔄 **Do-While Loops**
The `do-while` loop works just like while, but it always runs the code block at least once before checking the condition—kind of like when you’re forced to try a new dish before deciding if you like it. 🍜

### **Example: Trying Weird Smoothies 🥤**
```kotlin
var smoothiesTried = 0

do {
    println("🥤 Trying smoothie number ${smoothiesTried + 1}")
    smoothiesTried++
} while (smoothiesTried < 3)
// Output:
// 🥤 Trying smoothie number 1
// 🥤 Trying smoothie number 2
// 🥤 Trying smoothie number 3
```