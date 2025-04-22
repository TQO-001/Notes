---

## tags: [programming, control-structures, logic, design, loops, decisions] aliases: [Chapter 4 Notes, Making Decisions, Repeating Actions]

# Chapter 4: Making Decisions and Repeating Actions

## 🎯 Objectives

By the end of this chapter, you should understand:

- How decision-making works in code using if, if-else, and switch/case structures
    
- How and when to use loops (while, for, do-while)
    
- The difference between pre-test and post-test loops
    
- Using flags and logical operators in decision logic
    
- The best practices for writing readable and maintainable control structures
    

---

## 🧠 Decision Structures

### ➤ Single-alternative (If-only)

```pseudocode
If userAge >= 18 then
    Display "Access granted"
```

### ➤ Dual-alternative (If-Else)

```pseudocode
If temperature > 30 then
    Display "Too hot"
Else
    Display "Just fine"
```

### ➤ Multiple-alternative (If-Else-If or Case/Switch)

```pseudocode
If grade = "A" then
    Display "Excellent"
Else if grade = "B" then
    Display "Good"
Else if grade = "C" then
    Display "Fair"
Else
    Display "Needs improvement"
```

> 💡 **Tip**: Use `else-if` chains for complex logic; switch/case when comparing one variable to multiple constant values.

### ✅ Real Code Example (JavaScript)

```javascript
let score = 85;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else {
    console.log("Grade: C or below");
}
```

---

## 🔁 Loop Structures

### ➤ Pre-test Loop (While)

```pseudocode
Get userInput
While userInput != "exit"
    Display userInput
    Get userInput
```

### ➤ Post-test Loop (Do-While)

```pseudocode
Do
    Get userInput
    Display userInput
While userInput != "exit"
```

### ➤ Count-controlled Loop (For)

```pseudocode
For counter = 1 to 5
    Display counter
```

### ✅ Real Code Example (Python)

```python
for i in range(1, 6):
    print(i)
```

---

## 🚩 Using Flags and Boolean Logic

A **flag** is a variable used to signal when a condition is met.

```pseudocode
found = false
index = 0
While index < list.length and found == false
    If list[index] == searchValue then
        found = true
    index = index + 1
```

> ⚠️ _Sidenote_: Flags help **control loop exits** cleanly, especially in search or validation problems.

### Logical Operators:

|Operator|Meaning|
|---|---|
|`AND`|All conditions must be true|
|`OR`|At least one must be true|
|`NOT`|Inverts the condition|

---

## 🧱 Structured vs. Unstructured Control

- Structured: Clear start/end, limited to one entry and exit point
    
- Unstructured: Includes `goto`, breaks flow, harder to read
    

> 🧼 _Best Practice_: Never use `goto` in modern programming. Stick to the structured forms.

---

## 📊 Diagram: Control Flow for If-Else

```text
         [Condition?]
             ↓
       ┌─────────────┐
       │  true       │
       ↓             ↓
[Do Action A]    [Do Action B]
```

---

## 🧩 Mini Quiz

1. **What’s the difference between a while loop and a do-while loop?**
    
2. **Why is structured logic preferred over unstructured?**
    
3. **Convert this code into a for loop:**
    

```pseudocode
counter = 1
while counter <= 10
    Display counter
    counter = counter + 1
```

4. **What does a flag variable do in a loop?**
    

---

## 📌 Chapter Summary

|Concept|Description|
|---|---|
|If/Else|Decision structures for branching logic|
|Loops|Allow repetition (while, do-while, for)|
|Flags|Used to indicate condition matches|
|Logical Operators|AND, OR, NOT — control complex conditions|
|Structured Programming|Encourages readable, maintainable code|

