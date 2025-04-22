# Chapter 1 – An Overview of Computers and Programming
---

> [!tip] ### Use Autism For Evil
> Learn good programming habits from the beginning to make your programs as user-friendly as possible.

#### 🖥 What Is a Computer?
A **computer** is an electronic device that processes data by following instructions. It consists of:

- **Hardware** – The physical components (keyboard, screen, CPU, etc.)
- **Software** – The instructions that tell the hardware what to do.

> 📝 **Note**: Without software, hardware is essentially useless.

---

#### 📦 Types of Software

|Type|Description|Examples|
|---|---|---|
|**System Software**|Manages computer hardware and creates an environment for application software|Windows, macOS, Linux|
|**Application Software**|Performs specific tasks for users|Word processors, games|

> 💡 **Sidenote**: Think of system software as the “stage” and application software as the “actors.”

---
#### Understanding Simple Program Logic

- **Syntax vs. Logic Errors**:  
    A program with syntax errors won't run. A program with correct syntax can still produce wrong results if the logic is flawed. Logic errors are often harder to find than syntax errors.
- **Language Doesn't Matter for Logic**:  
    Program logic can be written in any language. The logic stays the same regardless of the programming language or the hardware used.
- **Basic Program Steps**:
    - **Input**: Get data (e.g., `input myNumber`)
    - **Processing**: Do something with the data (e.g., `set myAnswer = myNumber * 2`)
    - **Output**: Show the result (e.g., `output myAnswer`)
- **Hardware is Irrelevant to Logic**:  
    Whether data comes from a keyboard, mouse, or microphone doesn’t matter to the logic. Likewise, output could go to a screen, printer, or storage device—the logic stays the same.    

---
## Understanding the Program Development Cycle 
A programmer’s job involves writing instructions, but a professional programmer usually does not just sit down at a computer keyboard and start typing (_apparently_). The program development cycle, which can be broken down into at least seven steps.

> [!info] ### 🪜 Steps in Programming
> 1. **Understand the problem**  
> 2. **Plan the logic** (using tools like flowcharts or pseudocode)  
> 3. **Code the program**  
> 4. **Translate the code into machine language** (compile/interpret)  
> 5. **Test the program**  
> 6. **Put the program into production**  
> 7. **Maintain the program**


![[SDLC.PNG]]

> ✍️ **Tip**: Planning before coding reduces bugs and makes debugging easier.

### 🧠 (1) Understanding the Problem

Before you write a single line of code, make sure you actually understand what the user _really_ wants—not just what they said.

> **Users think in outcomes.** You need to translate that into logic.

Yeah, you're used to thinking in terms of input → process → output. But when you're planning, flip it. **Start with the output**. What's the end goal? What should the program deliver?

**Then work backward:**
> What do we need to know (input)?
> What needs to happen with that data (processing)?

And most importantly—**don’t take the request at face value**. It might seem simple (“Give me a list of employees with 5+ years here”), but _dig deeper_:

- Do they mean full-time only? What about contractors?
- Continuous service, or total time across gaps?
- What date are we using to measure that 5 years?
- Cutoff date—is it today, next Friday, or event-specific?
- What details should be included? Names? IDs? Emails? SSNs (yikes)? How’s it sorted—alpha? seniority? grouped by department?

**None of these decisions are yours to make**—they belong to the user. Your job is to ask the right questions until the fog clears.

> Basically: **vague specs = bugs waiting to happen**. Clear it up before you build anything.

---
#### 📎 Docs, Vibes, and Developer Intuition

You’ll usually get some documentation (**hopefully**)—maybe a rough request, some sample outputs, or data descriptions. _Don’t sleep on these. They’re your map_.

> Sometimes the user doesn’t even know what they want. 
> Sometimes they _think_ they do—until they see it. Be ready to iterate.

If you're working on **mobile apps**, it's even trickier:

> Users often don’t know they want your app until they have it.
> You’re designing for every kind of person (and **screen size**).    
> The market shifts fast—hardware, expectations, UX trends. You gotta stay agile.

> [!tip] ### Use Autism For Evil
> At the end of the day, a good dev is part **engineer**, part **detective**, part **therapist** and part **suicidal maniac**

---
### 🔧 (2) Plan the Logic – Your Blueprint

> [!tip] ### Use Autism For Evil
> Once you understand the problem, it’s time to plan **how** to solve it. This is the step where you lay out the logic that will guide your program.

#### Flowcharts: 
- Visualize the steps and decisions with easy-to-understand diagrams.

| Name                       | Description                                                |
| -------------------------- | ---------------------------------------------------------- |
| **Start/End (Terminator)** | Used to represent the start or end of a process.           |
| **Process**                | Represents a process, operation, or action.                |
| **Decision**               | Used to represent a decision point (yes/no or true/false). |
| **Input/Output**           | Represents data input or output operations.                |
| **Arrow (Flowline)**       | Represents the flow of control or data in the process.     |
| **Connector**              | Used to connect two different parts of the flowchart.      |
|                            |                                                            |

![[Symbols-of-Flowchart-1.jpg]]

---
#### Pseudocode:
- Write the steps in plain English (or pseudo-code) to structure your thoughts.

```
START
    // Declare variables
    DECLARE num1, num2, sum

    // Prompt user for input
    OUTPUT "Enter the first number:"
    INPUT num1

    OUTPUT "Enter the second number:"
    INPUT num2

    // Perform addition
    sum = num1 + num2

    // Display the result
    OUTPUT "The sum of", num1, "and", num2, "is", sum

END
```

Explanation of Pseudocode:
1. **START**: Marks the beginning of the program.
2. **DECLARE**: Declares variables that will hold data.
3. **OUTPUT**: Prints a message to the screen.
4. **INPUT**: Takes user input and stores it in a variable.
5. **sum = num1 + num2**: Adds the two numbers together.
6. **END**: Marks the end of the program.

---
#### IPO Charts: 
- Break down the Input → Processing → Output in clear categories.

![[Input-Process-Output-IPO-Diagram.png]]

---
#### 🧩 UML Diagrams:
- Use visual diagrams to plan system structure and behavior.
- Common types: Class, Use Case, Sequence, Activity, State.

![[UML Class Diagram.png]]


> These tools help organize your thoughts, but the core goal is always the same: clearly **map out each step** before writing a single line of code.
---
#### **Desk-Checking the Logic**:
This is a crucial step. Desk-checking means going through the program logic **on paper first**—you literally walk through each step mentally and see if it makes sense. This ensures you’re covering all bases before diving into actual coding.

#### **Consider Edge Cases**:
It’s important to consider the unexpected scenarios—what if the user provides invalid input? What happens if you get extreme values (like zero or negative numbers)? What if a required field is missing? Think about how your program will behave in these cases and plan accordingly.

#### **Big Picture**:
During this stage, you’re developing an **algorithm**—a step-by-step procedure to solve the problem. This is the framework that guides your program development, and it’s often the **most important phase** of programming. Solid planning upfront saves you from countless headaches later.

---
Absolutely—here’s a dev-friendly, standalone breakdown of the **“Coding the Program”** section, in the same style as before:

---

### 💻 (3) Coding the Program – Bringing Logic to Life

> [!tip] ### Use Autism For Evil
> Once the logic is mapped out, _then_ (and only then) do you jump into writing the actual code.

#### Choosing a Language
There are hundreds of programming languages out there. The one you choose depends on:
- The type of project (web, data science, embedded, etc.)
- The tools/libraries available
- Performance needs
- Team preferences or existing codebase

Each language has its quirks, but **at their core, they all do the same basic stuff**:
- Handle input
- Do some processing (math, logic, etc.)
- Output results

> So, once you’ve got solid logic, you can implement it in just about any language.

> [!tip] ### **Syntax Comes _After_ Logic**
You only start worrying about things like punctuation, brackets, semicolons, and correct keywords **once** you start coding. That’s syntax. It’s like the grammar of a language—you don’t need to think about it while brainstorming what your app does.

#### **Some Pros Code and Plan at the Same Time**

Sure, some experienced devs can think through the logic _while_ they’re typing it out (especially for small, simple programs). But for anything real—apps, systems, games, business tools—**planning comes first**, just like you wouldn’t start shooting a movie without a script.

#### **What’s Harder—Planning or Coding?**

Coding might _feel_ harder at first because of all the rules and weird symbols, but honestly? **Planning is the real challenge**. Writing code is like translating—once you know what to do, turning it into JavaScript, Python, or C# is just mechanics.

Think of it like this:

- **Planner = Story Creator**
    
- **Coder = Translator**
    

Who gets paid more? Who gets the credit? 😏

---

Want me to bundle this and the previous sections into a full doc or cheat sheet?
---
#### 🔠 Machine Language, High-Level Languages, and Translators

|Language Type|Description|
|---|---|
|**Machine Language**|Binary code (1s and 0s) the computer directly understands|
|**High-Level Language**|More readable and closer to human language (like Python, Java)|
|**Translators**|Convert high-level code into machine language (e.g., compilers, interpreters)|

> 🧪 **Example**: Writing `print("Hello")` in Python is high-level. A compiler turns it into 010101... for the computer.

---

#### 🔀 Flowcharts and Pseudocode

- **Flowchart** – Visual diagram of logic flow using symbols.
    
- **Pseudocode** – Plain English version of logic, structured like code.
    

> ✅ **Tip**: Use pseudocode when you need to plan out logic without getting stuck on syntax.

---

#### 📐 Variables and Data Types

Variables store data that programs use and manipulate.

|Data Type|Example|
|---|---|
|Integer|42|
|String|"Hello"|
|Boolean|True / False|

> 🧠 **Sidenote**: Naming variables clearly (like `userAge` instead of `x`) makes your code readable and maintainable.

---

### 🛠 Real-Life Programming Example

Imagine writing a program to calculate someone's age:

```pseudocode
Start
    Get current year
    Get user's birth year
    Subtract birth year from current year
    Display result
End
```

---

### ⚙️ Compiling vs. Interpreting

- **Compiler**: Converts the whole program to machine code before running.
    
- **Interpreter**: Converts and runs code line-by-line.
    

||Compiler|Interpreter|
|---|---|---|
|Speed|Faster after compile|Slower overall|
|Error Check|Catches errors at once|Catches during execution|

---

### ✨ Summary Notes

- Computers follow step-by-step instructions.
    
- Programs must be well planned and logically structured.
    
- Understanding variables, data types, and the flow of execution is foundational.
    
- Translators are crucial to convert human-readable code into machine language.
    

---

Would you like to continue to **Chapter 2** next, or should I format this into a markdown file for you to download and import directly into Obsidian?