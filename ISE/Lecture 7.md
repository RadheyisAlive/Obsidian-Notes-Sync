![[Lecture7_Modularity_1pp_2024_S1_V1.pdf]]

**Software Design: Building Blocks for Great Software**

Imagine you're building a house. You wouldn't just start stacking bricks randomly, right? You'd have a plan – a blueprint – that outlines the different rooms, their purposes, and how they connect. Software design is like that blueprint. It's the roadmap that guides how you build your software, ensuring it's well-organized and easy to maintain.

**Modularity: Divide and Conquer**

Just as a house has different rooms for specific purposes (kitchen, bedrooms, etc.), software is divided into smaller pieces called modules. Each module has its own job, like calculating a price, handling user input, or storing data. This "divide and conquer" approach makes it easier to manage complexity.

**Maintenance: Software Needs Check-ups Too**

Think of software like a car – it needs regular maintenance to keep running smoothly. Even after software is released, it often needs updates to fix bugs, add new features, or adapt to changes in the environment.

**Two Key Ideas for Good Design**

1. **Coupling (Interdependence):** How tightly different modules are connected.
    - **Low Coupling (Good):** Modules are like independent rooms. You can change one without affecting the others much.
    - **High Coupling (Bad):** Modules are like a tangled mess of wires. Changing one can cause problems in others.
2. **Cohesion (Focus):** How well a module focuses on a single task.
    - **High Cohesion (Good):** A module does one thing really well, like a specialized tool.
    - **Low Cohesion (Bad):** A module tries to do too many things, like a Swiss army knife trying to be a screwdriver, a saw, and a corkscrew all at once.

**Avoiding Redundancy: Don't Repeat Yourself**

Imagine copying the same paragraph over and over in a document. It would be a waste of space and make it harder to find what you're looking for. Similarly, in software, avoid repeating the same code. Instead, create one good version of it and reuse it where needed.

**Refactoring: Spring Cleaning for Code**

Think of refactoring as tidying up your room. You're not changing what you own, but you're organizing it so it's easier to find things and keep the room neat. In software, refactoring means changing the code's internal structure to make it more readable, easier to understand, and simpler to modify in the future.

**In Summary**

- **Software design** is all about planning and structuring your code.
- **Modularity** breaks down complexity into manageable pieces.
- **Maintenance** keeps software healthy and up-to-date.
- **Low coupling** and **high cohesion** are design goals that make software easier to maintain.
- **Avoid redundancy** to keep your code clean and efficient.
- **Refactoring** is like a spring cleaning for your code.

Reuse (a good thing) actually increases coupling (a bad thing) , therefore  
have to consider carefully.  

![[Worksheet7_Modularity_2024_V1.pdf]]

- **Discussion:**  
    (a) **Global constants and modularity:** Global constants can create modularity problems because they tightly couple modules to specific values. If these constants are used widely throughout the codebase, modifying them requires changes in multiple places, increasing coupling and reducing modularity. However, if used judiciously and for truly constant values, they may not significantly impact modularity.
    
    (b) **Methods/functions with many parameters and coupling:** When a method/function takes a large number of parameters, it can lead to a high level of coupling because the caller must know and provide all these parameters. This tightly binds the caller to the implementation details of the method, increasing coupling between them.
    
    (c) **Avoiding code duplication:** Code duplication should be avoided because it leads to redundancy, making maintenance difficult and error-prone. If a change is required in duplicated code, it needs to be applied to all instances, increasing the likelihood of errors and inconsistencies. While complete elimination of duplication may not always be feasible, reducing it through techniques like abstraction and reuse improves maintainability.
    
- **Checklist for modularity issues:**  
    Constructing a checklist involves identifying specific modularity issues and formulating questions to address them. This checklist should cover areas such as coupling, cohesion, and redundancy. Each question should prompt a yes-or-no answer, indicating whether the issue exists in the code being reviewed.  
    

To conduct a code review of the provided Python program for modularity issues, let's analyze the code against the checklist and identify potential improvements:

  

![[Statistics(2).py]]

### Checklist for Modularity Issues

|   |   |   |
|---|---|---|
|Item|Checklist Question Related to Modularity|Description of the Issue if 'No' is the Answer|
|1|Are global variables minimized or avoided?|Global variables like `sumLength`, `sumList`, and `varianceResult` are used across multiple functions, increasing coupling. This can lead to unintended side effects and difficulty in tracking dependencies.|
|2|Are functions/methods narrowly focused on single tasks?|Functions like `mySum()`, `mean()`, `variance(dataList)`, `stddev(dataList)`, `minmax(dataList, calcMax)`, and `product(op, dataList)` perform calculations but also rely on global state (`sumLength`, `sumList`). This reduces cohesion as these functions mix computation with state management.|
|3|Is there any unnecessary redundancy in the code?|The functions `minmax(dataList, calcMax)` have duplicated logic for finding min and max values, which could be consolidated into a single function with a parameter for direction (`min` or `max`).|
|4|Are there magic numbers or non-descriptive variable names?|Constants like `1`, `2` for different operations (`geommean`, `log`) should be replaced with named constants for clarity (`GEOMETRIC_MEAN_OPERATION`, `LOG_OPERATION`).|

### Modularity Issues Identified

1. **Global Variables:** The use of `sumLength`, `sumList`, and `varianceResult` as global variables affects modularity by increasing coupling between functions. These variables are accessed and modified by multiple functions, reducing encapsulation and making it harder to reason about the program flow.
2. **Function Cohesion:** Functions like `mySum()`, `mean()`, `variance(dataList)`, `stddev(dataList)`, `minmax(dataList, calcMax)`, and `product(op, dataList)` should ideally focus strictly on their computational tasks. However, they also manage global state (`sumLength`, `sumList`), which mixes concerns and reduces clarity.
3. **Redundancy:** The `minmax(dataList, calcMax)` function contains duplicated logic for finding either the minimum or maximum value. This can be refactored into a single function that takes a parameter to determine whether to find the min or max, thereby reducing redundancy and improving maintainability.
4. **Magic Numbers:** Constants `1` and `2` used in `product(op, dataList)` for operations (`geometric mean` and `log`) should be replaced with named constants for better readability and maintainability.

### Refactoring to Improve Modularity

**(a) Fixes:**

1. **Encapsulation of State:** Refactor functions to reduce reliance on global variables (`sumLength`, `sumList`, `varianceResult`). Pass necessary data explicitly through function parameters and return values to improve encapsulation and reduce coupling.
2. **Enhanced Cohesion:** Separate concerns more clearly by ensuring each function performs a single, well-defined task without mixing state management with computation. For example, `mean()` should only calculate the mean and not handle list management.
3. **Consolidate Logic:** Merge duplicate logic in `minmax(dataList, calcMax)` into a single function that accepts a parameter (`calcMax`) to determine whether to find the min or max value.
4. **Use of Constants:** Replace magic numbers (`1`, `2`) with descriptive constants (`GEOMETRIC_MEAN_OPERATION`, `LOG_OPERATION`) to improve code readability and maintainability.

**(b) Implementation:** Implement the above fixes in the Python program by modifying function definitions and usage where necessary.

**(c) Testing:** Ensure that after refactoring, the program still performs the intended calculations correctly by running test cases for each operation (`sum`, `mean`, `variance`, `stddev`, `minmax`, `product`, `geommean`).

**(d) Checklist Verification:** Validate the refactored code against the modularity checklist to confirm that identified issues have been effectively addressed.

By following these steps, the Python program can be refactored to enhance modularity, thereby improving maintainability and reducing potential errors associated with high coupling and low cohesion.