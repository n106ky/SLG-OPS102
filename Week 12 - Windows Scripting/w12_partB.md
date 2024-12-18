# PART B: Create Your Own Cheat Sheet!

> 💡 **Tip: A personalized cheat sheet will help you quickly review before the final exam!**
> 
> - Refer to these hints to structure your answers for each feature.
> - Summarize key concepts, commands, and examples that you’ve learned in this course.    
> - Provide examples of code for both scripting styles to complete the table.
>   
>  ⚠️ **Caution:**  
> - The content stated here might not cover all course materials.
> - You should also revise using the **official course notes** provided by your professor.

## Comparison of Scripting in Windows and Linux

| **Feature**           | **Windows Batch Scripting** | **Linux Bash Scripting** |
|------------------------|-----------------------------|----------------------------|
| **Variable Assignment** <br> - How to assign a value to a variable? <br> - How to prompt user input?  <br> - Are they case-sensitive?  <br> - How to escape special characters in strings or variables? | | |
| **Variable Usage** <br> - How to display a variable’s value? <br> - How to perform arithmetic operations? <br> - How to compare values?  | | |
| **Arithmetic Operations** <br> - How do you enable arithmetic calculations in a script? <br> - What operators are available?  <br> - What types of numbers can be used in calculations?  | | |
| **String Comparisons** <br> - How to compare strings? <br> - Are the comparisons case-sensitive? | | |
| **Integer Comparisons** <br> - How are numbers compared? <br> - What operators are available? | | |
| **Environment Variables** <br> - How to access and apply Error Codes?  <br> - How can you view all environment variables? <br> - What are some other useful environment variables? | | |
| **Conditionals** <br> - How to implement conditional logic with `if`? <br> - How to handle multiple conditions? | | |
| **Loop Types** <br> - What types of loops are supported? <br> - How do they differ in functionality? <br> - Is the variable being updated in each loop?  | | |
| **Parameters** <br> - How can we list all the parameters that were received?  <br> - How many parameters were received? <br> - How can we use parameters?  | | |


## Control Flow Commands

| **Feature**       | **Windows Batch Scripting**                          | **Linux Bash Scripting**                                   |
|-------------------|------------------------------------------------------|----------------------------------------------------|
| **GOTO**          | Jumps to a `label` in the script.                      | Not supported. <br> Use functions or structured logic i.e. `if`.  |
| **Continue**       | Not supported                                        | `continue` skips the current loop iteration.       |
| **Break**         | Exit a loop using `exit /b`.                         | `break` exits the current loop.                    |
| **Error Handling**| Use `GOTO` to handle errors or branching.            | Use functions or conditionals for error handling.  |
| **Shift**         | Shifts positional parameters to the left (e.g., `%1` becomes `%2`).  | Same as Windows |
