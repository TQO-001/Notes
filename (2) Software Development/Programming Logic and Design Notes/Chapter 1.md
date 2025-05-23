# Chapter 1 – An Overview of Computers and Programming
---

> [!tip] ### Use Autism For Evil
> **_Learn good programming habits from the beginning to make your programs as user-friendly as possible._**

- **_Procedural programming_** is a programming model that focuses on the procedures that programmers create. 
- **_Object-oriented programming_** is a programming model that focuses on objects, or “things,” and describes their features (also called attributes) and behaviors.

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
> [!tip] ### Autism For Evil
> **_Try To code for future case_**
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

![[The program development cycle.PNG]]

> ✍️ **Tip**: Planning before coding reduces bugs and makes debugging easier.

The Program Development Cycle(PDC) is similar if not the same as the Software Development Life Cycle (SDLC), but for now just focus on learning this, learning doer.

![[6-Stages-of-Software-Development-Life-Cycle.jpg]]

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

> [!tip] ### Autism For Evil
> **_At the end of the day, a good dev is part engineer, part detective, part therapist, and part suicidal maniac_**

---
### 🔧 (2) Plan the Logic – Your Blueprint
> [!tip] ### Autism For Evil
> **_Once you understand the problem, it’s time to plan how to solve it. This is the step where you lay out the logic that will guide your program._**

> As you learn to create pseudocode and flowchart statements, you will develop a sense for how much detail to include. The statements represent the main steps that must be accomplished without including minute points. The concept is similar to writing an essay outline, in which each statement of the outline represents a paragraph.

![[Flowchartandpseudocode.PNG]]

Programmers seldom create both pseudocode and a flowchart for the same problem. You usually use one or the other. In a large program, you might even prefer to write pseudocode for some parts and to draw a flowchart for others.

#### Pseudocode:
> Write the steps in plain English (or pseudo-code) to structure your thoughts.

> [!tip] ### Autism For Evil
> **_Anything you can describe in pseudo-code that is grounded in reality.
> As long as it doesn't requires direct use of any magic/miraculous expectations._**

- Pseudocode is an English-like representation of the logical steps it takes to solve a problem. `Pseudo` is a prefix that means false, and to `code` a program means to put it in a programming language. Therefore, pseudocode simply means "false code," or sentences that appear to have been written in a computer programming language but do not necessarily follow all the syntax rules of any specific language.

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

Summarized explanation of Pseudocode:
1. **START**: Marks the beginning of the program.
2. **DECLARE**: Declares variables that will hold data.
3. **OUTPUT**: Prints a message to the screen.
4. **INPUT**: Takes user input and stores it in a variable.
5. **sum = num1 + num2**: Adds the two numbers together.
6. **END**: Marks the end of the program.

> [!note] ### **Pseudocode Standards**
> - Programs begin with `start` and end with `stop`; these two words are always aligned.
> - Whenever a module name is used, it is followed by a set of parentheses.
> - Modules begin with the module name and end with `return`. The module name and `return` are always aligned.  
> - Each program statement performs one action— for example, input, processing, or output.
> - Program statements are indented a few spaces more than `start` or the module name.
> - Each program statement appears on a single line if possible. When this is not possible, continuation lines are indented.
> - Program statements begin with lowercase letters.
> - No punctuation is used to end statements.

---
#### Flowcharts: 
> A flowchart is a pictorial representation of the same thing.

- Visualize the steps and decisions with easy-to-understand diagrams.

| Name                       | Description                                                |
| -------------------------- | ---------------------------------------------------------- |
| **Start/End (Terminator)** | Used to represent the start or end of a process.           |
| **Process**                | Represents a process, operation, or action.                |
| **Decision**               | Used to represent a decision point (yes/no or true/false). |
| **Input/Output**           | Represents data input or output operations.                |
| **Arrow (Flowline)**       | Represents the flow of control or data in the process.     |
| **Connector**              | Used to connect two different parts of the flowchart.      |

![[Symbols-of-Flowchart-1.jpg]]

> Some software programs that use flowcharts (such as Visual Logic) use a left-slanting parallelogram to represent output. As long as the flowchart creator and the flowchart reader are communicating, the actual shape used is irrelevant.
---
#### 🧩 UML Diagrams:
- Use visual diagrams to plan system structure and behavior.
- Common types: Class, Use Case, Sequence, Activity, State.

![[UML Class Diagram.png]]

---
#### IPO Charts: 
- Break down the Input → Processing → Output in clear categories.

![[Input-Process-Output-IPO-Diagram.png]]

---
> These tools help organize your thoughts, but the core goal is always the same: clearly **map out each step** before writing a single line of code.
---
#### **Desk-Checking the Logic**:
This is a crucial step. Desk-checking means going through the program logic **on paper first**—you literally walk through each step mentally and see if it makes sense. This ensures you’re covering all bases before diving into actual coding.

#### **Consider Edge Cases**:
It’s important to consider the unexpected scenarios—what if the user provides invalid input? What happens if you get extreme values (like zero or negative numbers)? What if a required field is missing? Think about how your program will behave in these cases and plan accordingly.

#### **Big Picture**:
During this stage, you’re developing an **algorithm**—a step-by-step procedure to solve the problem. This is the framework that guides your program development, and it’s often the **most important phase** of programming. Solid planning upfront saves you from countless headaches later.

---

### 💻 (3) Coding the Program 

> [!tip] ### Autism For Evil
> **_Once the logic is mapped out, then (and only then) do you jump into writing the actual code._**

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

#### Some Pros Code and Plan at the Same Time

Sure, some experienced devs can think through the logic _while_ they’re typing it out (especially for small, simple programs). But for anything real—apps, systems, games, business tools—**planning comes first**, just like you wouldn’t start shooting a movie without a script.

#### What’s Harder—Planning or Coding?

Coding might _feel_ harder at first because of all the rules and weird symbols, but honestly? **Planning is the real challenge**. Writing code is like translating—once you know what to do, turning it into JavaScript, Python, or C# is just mechanics.

Think of it like this:
- **Planner = Story Creator**
- **Coder = Translator**

> [!tip] ### Autism For Evil
> **_The way that I like to think about it is that code/syntax is like lego blocks, putting pieces of code together, you could use your creativity and let your imagination run wild, but even the most obtuse or abstract creation has an end goal and for smaller projects its good to show off and let you imagination run wild_**

---
### ⚙️ (4) Translate the code into machine language
No matter what language you write your code in, your computer **only understands one language**: **machine language** (aka binary: 1s and 0s).

Why? Because at the hardware level, a computer is just an insane number of tiny switches. They’re either **on** (`1`) or **off** (`0`). That’s it. No `print()`, no `if`, no fun keywords. Just electricity.

#### 💡 So how does your code run?

Thanks to translator programs called:
- **Compilers** – Translate all your code at once into machine code
- **Interpreters** – Translate and run your code **line-by-line**

These tools **convert your human-friendly code** into raw machine instructions your CPU can actually execute.

#### ✅ Syntax Matters (but isn’t the worst)

If your code has a **syntax error** (misspelling, bad grammar, missing punctuation, etc.), the compiler/interpreter stops and throws an error. That’s good—it _protects_ you from running broken stuff.

Think of it like this:

> You write: `The dg chase the cat.`  
> The compiler says: ❌ "What’s dg?"  
> You fix it to: `The dog chase the cat.`  
> Compiler: ❌ "Still wrong. Verb doesn't match subject."  
> You realize: Oh, should be `dogs chase` **or** `dog chases`.

> [!tip] ### Autism For Evil
> **_The tool doesn’t know what you meant, but it knows what’s allowed. Syntax errors are super common and easy to catch—don’t sweat them. You'll fix a bunch every time you compile._**

> [!tip] #### 🔁 Typical Workflow:
> 1. **Plan the logic**
> 2. **Write the code**
> 3. **Compile → get errors**
> 4. **Fix → compile again**
> 5. **Repeat until clean**


Every compile is like a spellcheck pass for your logic. Once it's syntax-error free, _then_ the magic happens—it gets turned into 1s and 0s and handed off to the machine.
 
### 🧪 (5) Test the program
Just because your program compiles and runs without errors doesn’t mean it’s correct.

> ✅ Syntax ≠ ✅ Logic

You can have **perfect syntax** and still get completely wrong results if your logic is flawed. That’s called a **logical error**—and those are way sneakier.

#### 🧠 What’s a Logical Error?
It’s when your code **_technically works_**, but does the _wrong thing_.  
Example:

```plaintext
input myNumber  
set myAnswer = myNumber * 20  
output myAnswer
```

No syntax issues here. But if your goal was to double the input, multiplying by 20 is just wrong. It's a logic fail—not a compiler fail.

#### 🔍 Testing = Executing + Observing
Once your program compiles, **you test it by running it with sample data** and checking the output. If the output doesn’t match what’s expected, it’s time to debug.

Example:

```plaintext
input myNumber  
set myAnswer = myNumber + 2  
output myAnswer
```

If you input `2`, you get `4`—looks right? Not if the goal was to double it. Try `7` and now you get `9`. Boom: logic error exposed.

---

#### 🐞 **Debugging – _Your New Hobby_**

**Debugging** is the process of finding and fixing logic errors in your code. You do it by:

- Running the program with different data sets
- Verifying output matches expectations
- Tracing values through each step to spot what’s going sideways

> [!note] ### Remember
logic errors won’t stop your program—they’ll just make it give the wrong answers.

---

#### 🎯 **Test with Intention**

**Smart testing is key**. Don’t just use ideal cases. Try edge cases, too:

- New vs. old employees
- Zero values, negative numbers, extremely high numbers
- Unexpected input (like nulls, or input in the wrong format)
- Unusual behaviors (e.g., an employee with 15 dependents, or a customer ordering 10,000 items)

Real-world bugs often hide in these oddball scenarios.

> [!tip] ### 🧠 Rule of thumb:
>  If you only test with perfect data, you’ll only get _perfectly broken_ programs.

---
### 🚀 (6) Put the program into production
After all the planning, coding, testing, and debugging... it’s finally time to ship.

> **Production = real users, real data, real stakes.**

Once your program is fully tested and working correctly, it’s ready to go live. But “going live” doesn’t always mean just hitting **Run**.

#### ✅ Two Kinds of Deployments:
1. **One-and-done**
    - If it’s a small, one-time report or tool, production might just mean running the program once and sending off the results. Easy.
2. **Ongoing or System-Level**
    - If the program is part of a larger system or will be used regularly (daily, weekly, etc.), things get more serious.

#### 🔄Production = More Than Just Code
Before a program can be fully used in a business, a few real-world steps often need to happen:
- **Training**: Staff might need training to use the new system or input data correctly.
- **Data Conversion**: You might need to reformat or migrate existing data to work with the new system.
- **User Adoption**: End-users need to understand the output and how it fits into their workflow.
- **Infrastructure Updates**: Sometimes you’ll need to prep servers, storage, networks, or devices.

#### 🛠️ **Conversion = The Big Switch**
This is the full transition process—everything from moving legacy data into the new system, to training people, to ensuring all systems work together.

> In big orgs, conversion can take **months** or even **years**, especially if it involves critical systems, regulatory constraints, or a ton of interdependent software.

> [!tip] ### Autism For Evil
> **_So yeah, writing the code is only half the battle. Getting it into the hands of users, making sure it works for them, and ensuring it fits into the company’s operations—that’s the real finish line._**

---
### 🔧 (7) Maintain the program
Once your program is live, your job isn’t over. Things change. Laws change. Users change their minds. Systems evolve. **That’s where maintenance comes in.**

> **Maintenance = making updates to live programs** to keep them accurate, functional, and relevant.

#### 🧩 Why Maintenance Happens:
- **New rules** (e.g., updated tax rates)
- **Changes to input data** (e.g., new file formats or API responses)
- **User requests** (e.g., extra fields, updated reports, new features)
- **Bug fixes** (because nobody’s perfect)
- **Performance improvements** (e.g., optimize slow queries or reduce memory usage)

#### 🧠 You’ll Probably Start Here
If it’s your first programming job, chances are you’ll be doing **maintenance work on existing codebases**. This means:

- Reading someone else’s code
- Understanding what it does
- Making safe, clean updates

And when you’re in this role, you’ll _deeply appreciate_:

- Clear code structure
- Descriptive variable names
- Good documentation

**_Because bad code with no comments = pain._**

#### ♻️ Maintenance = Mini Dev Cycle
Any time you make a change, you repeat the same process:

1. **Understand** the new requirement
2. **Plan** the logic
3. **Code** the update
4. **Translate/compile** if needed
5. **Test** the change thoroughly
6. **Deploy** the fix or update to production

#### 🪦 When to Let Go
If too many changes pile up, the old program might be scrapped altogether. When a system is no longer maintainable (too outdated, too messy, or no longer fits the business), it’s time to start over and rebuild.

> Think of it like renovating an old house—sometimes it’s better to just rebuild from the ground up.

---
