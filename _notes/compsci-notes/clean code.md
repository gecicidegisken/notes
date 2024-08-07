---
title : clean code
feed: show
date : 01-03-2024
tags: ["clean code"]
summary: My reading notes on clean code lectures by Uncle Bob
---


references: 
[video](https://www.youtube.com/watch?v=7EmboKQH8lM&list=PLUxszVpqZTNShoypLQW9a4dEcffsoZT4k&index=1)

---


### **clean variable names**

- Reveal your intent with the name
- Single letter variable names are acceptable in their scope
- If the scope of a variable is small, name of the variable can be small (and vice versa)
- Names should be clear and don’t create ambiguity between other similar named variables

### **clean comments**

- comments are used if the code can’t explain itself, and comments do not make up for bad code. instead of writing comments to explain bad code, just clean up your code.
- comments are useful to explain the context, to give intention or explaining regex (where you don’t get reading)
- docstrings are very useful (actually necesssary imho) expecially for external APIs
    - for example backend docstrings for frontend
- do not markup docstrings, they need to be readable in code as well as they are in docstring generator tool
- journal comments (date-change) are not needed, we already have git (or any other vcs)
- commented out code should be avoided if possible
- comments should be related to current code. do not comment about code in somewhere else. if that code changes your comment is outdated

### **clean functions**

- Functions need to be small, they should do **one thing well**
    - If you can’t extract something from a function to create a new function, that’s one thing.
    - By this logic,a function’s indent level is best 1-2
- If a function requires 4+ arguments, just take a second to think about why these arguments are not an object (or similar data structure)
- Passing a boolean argument is bad practice. Just have 2 different functions to be called when the boolean or !boolean
    - This is exceptional sometimes
- A side effect is when you call a function and that function changes the state of the system. We don’t usually want side effect functions
    - Like opening a file and keeping it open or allocating a memory.
    - This is what garbage collections are about
    - The convention here is if a function is void (does not return a value) it has side effects, if it returns a value, you need to make sure it does not change the state of the system in any way.
- DRY → don’t repeat yourself
    - Consider converting copied and pasted code chunks to functions