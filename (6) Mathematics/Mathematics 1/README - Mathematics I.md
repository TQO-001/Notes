# Mathematics for Programming

## 1. Binary Numbers

Binary is a **base-2 number system** that uses only two digits: `0` and `1`. It is the fundamental numbering system used by computers because electronic circuits have two states: **ON (1) and OFF (0)**.

### **Why Use Binary in Computing?**

- Computers use electrical signals (ON/OFF).
- More reliable than decimal in circuits.
- Forms the foundation of all modern computing operations.

### **Binary vs. Decimal Comparison Table**

|Decimal|Binary|Explanation|
|---|---|---|
|0|0000|All bits are 0|
|1|0001|Last bit is 1|
|2|0010|1 shifts left|
|3|0011|2 + 1 (last two bits 1)|
|4|0100|2² (third bit set)|
|5|0101|4 + 1|
|6|0110|4 + 2|
|7|0111|4 + 2 + 1|
|8|1000|2³ (fourth bit set)|

### **Converting Decimal to Binary (Division Method)**

1. Divide the decimal number by 2.
2. Record the remainder (0 or 1).
3. Continue dividing the quotient by 2 until you reach 0.
4. Read the remainders **from bottom to top**.

**Example:** Convert `13` to Binary

```
13 ÷ 2 = 6  → remainder 1  
6 ÷ 2 = 3   → remainder 0  
3 ÷ 2 = 1   → remainder 1  
1 ÷ 2 = 0   → remainder 1  
```

**Binary Representation: `1101`**

### **Converting Binary to Decimal**

Multiply each binary digit by powers of `2` and sum the results.

**Example:** Convert `1011` to Decimal

```
(1 × 2³) + (0 × 2²) + (1 × 2¹) + (1 × 2⁰)  
= 8 + 0 + 2 + 1  
= 11 (decimal)
```

Your notes are already on the right track! Here's an adjusted version with a more thorough breakdown of the **binary addition** you provided:

---

### **Binary Arithmetic**

- **Addition:** Same as normal addition, but it only uses `0` and `1`. The key rules are:
    - `0 + 0 = 0`
    - `0 + 1 = 1`
    - `1 + 0 = 1`
    - `1 + 1 = 10` (carry over the 1)
    - `1 + 1 + 1 = 11` (carry over the 1)

### **Binary Addition Example:**

Let's break down the addition of **1101** and **1001**:

```
   1101  
+  1001  
--------
```

Step-by-step:

1. **Rightmost column:**
    
    - **1 + 1 = 10**.
    - Write down `0`, and carry over the `1`.
2. **Second column:**
    
    - **0 + 0 + 1 (carry)** = **1**.
    - No further carry.
3. **Third column:**
    
    - **1 + 0 = 1**.
    - No carry.
4. **Leftmost column:**
    
    - **1 + 1 = 10**.
    - Write down `0`, and carry over the `1`.

Now, the final result is:

```
   1101  
+  1001  
--------
  10100  
```

So, **1101 + 1001 = 10100** in binary.

---

### **Key Takeaways:**

- The main principle in binary addition is **carry over** when the sum of two digits is `2` or greater (just like how in decimal addition, sums of `10` or greater are carried over).
- After completing the addition from right to left, you write down the results in the correct position, just like in regular addition.

### **Other Operations:**

- **Subtraction:** Follows the same principles as decimal subtraction, but you may need to borrow if the top digit is smaller than the bottom one.
- **Multiplication:** Works just like decimal multiplication but with only `0`s and `1`s. The process is often simpler because `1` times anything is just that number, and `0` times anything is `0`.
- **Division:** Binary division can be done using repeated subtraction or the long division method, much like decimal division.

---

## 2. Fibonacci Sequence

The **Fibonacci sequence** is a series where each number is the sum of the two preceding ones.

### **Formula:**

F(n)=F(n−1)+F(n−2)F(n) = F(n-1) + F(n-2)

where

- F(0)=0F(0) = 0,
- F(1)=1F(1) = 1,
- F(2)=1F(2) = 1,
- F(3)=2F(3) = 2,
- F(4)=3F(4) = 3, etc.

### **First Few Fibonacci Numbers**

|n|Fibonacci Number|
|---|---|
|0|0|
|1|1|
|2|1|
|3|2|
|4|3|
|5|5|
|6|8|
|7|13|
|8|21|
|9|34|

### **Fibonacci in Programming** (Recursive Approach in Python)

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(7))  # Output: 13
```

**Drawback:** Exponential time complexity O(2n)O(2^n).

### **Efficient Approach (Memoization)**

```python
def fibonacci_memo(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fibonacci_memo(n - 1, memo) + fibonacci_memo(n - 2, memo)
    return memo[n]

print(fibonacci_memo(7))  # Output: 13
```

### **Applications of Fibonacci Sequence**

- **Computer Algorithms:** Used in recursion and dynamic programming.
- **Data Structures:** Fibonacci heaps for priority queues.
- **Nature:** Spiral patterns in flowers and shells.
- **Finance:** Fibonacci retracement in stock market analysis.

---

## Summary

|Concept|Explanation|
|---|---|
|**Binary System**|Base-2 number system using 0s and 1s|
|**Decimal to Binary**|Divide by 2, record remainders, read from bottom up|
|**Binary to Decimal**|Multiply each bit by powers of 2 and sum|
|**Binary Arithmetic**|Uses bitwise addition, subtraction, multiplication, and division|
|**Fibonacci Sequence**|Series where each term is the sum of the previous two|
|**Recursive Fibonacci**|Simple but inefficient|
|**Memoized Fibonacci**|Optimized using caching|

---

This note is structured for easy reference in **Obsidian**, with tables, explanations, and code snippets. Would you like any modifications or additional details?