# Exercise: ATM Continue

## Objectives
Practice using the Matrix server (Linux) and apply what you've learned in this session to implement **loops** in a Bash script.  

**Recap 4 Types of Loops:**  
```for VARIABLE in LIST```: Iterates over items in a list.  
```for (( ; ; ))```: C-style loop, useful for specifying initialization, condition, and increment/decrement.  
```while EXPR```: Loops while the condition is true.  
```until EXPR```: Loops until the condition is met.  

You may refer to [Bash Scripting - 2](http://15.223.64.81/doku.php?id=ops102:bash_scripting_2_-_loops) course materials.

---
## Step-by-Step Instructions

In this exercise, you’ll use **for-loop**, **while-loop**, and **until-loop** to create an interactive ATM program.  


If you have not completed last week's exercise, you may travel back to [Week 10 folder](https://github.com/n106ky/SLG-OPS102/blob/main/Week%2010%20-%20Bash%20Scripting%20-%20i/w10_ATM_ANS.md)  and copy the code.

### Apply Loops in the Following Situations:

1. **Ask if the user would like to continue using the service**:
   - Use a **while-loop** to allow the user to continue selecting services until they choose to exit.

2. **Display the selection list**:
   - Use a **for-loop** to display the list of available services:
     - **Deposit**
     - **Withdrawal**
     - **Check Savings Account**
     - **Savings Plan**

3. **Validate User Input**:
   - **Service number**:
     - Use an **until-loop** to ensure the user selects a valid service number (1-4).
   - **Amount**:
     - Use a **while** or **until** loop to confirm the entered amount is a positive number.
   - **Continue variable**:
     - Use a **while** or **until** loop to verify the input for the "continue" variable is either **"Y"** or **"y"** or **"N"** or **"n"**.

---
## Sample Output
**If user chose Selection 1 & 2**  
```📌Also notice how the Savings amount got updated after Deposit and Withdrawal```  

<img src="https://github.com/user-attachments/assets/612ef468-2c20-4d64-8710-de329e9a972d" width="500">

---
## Key Bash Concepts

1. **Variables**:
   - Used to store initial values like the savings balance and user input.

2. **Input and Output**:
   - `read` captures user input, and `echo -e` displays messages with escape sequences like newlines for formatting.

3. **Conditional Statements**:
   - `if...elif...else` blocks control program flow based on the user’s choices.
   - `[[]]` syntax is used for conditions, and logical operators like `||` check multiple conditions.

4. **Loops**:
   - **While-loop**: Repeats actions based on conditions, e.g., to keep the program running until the user exits.
   - **For-loop**: Iterates over a list, e.g., to display service options.
   - **Until-loop**: Repeats prompts until valid input is given, ensuring user input correctness.

5. **Arithmetic Operations**:
   - `$(( ... ))` performs calculations, e.g., updating the savings balance.

6. **Date Commands**:
   - `date` retrieves the current date or calculates future dates with formatting options.

7. **Regular Expressions**:
   - **Purpose**: Used for input validation to ensure user entries are in the correct format, such as checking that the amount entered is a positive integer.
   - **Syntax**: Regular expressions in Bash use the `=~` operator within `[[ ... ]]` conditions to check for patterns.
   - **Example**:
     ```bash
     [[ "$AMT" -le 0 || ! "$AMT" =~ ^[0-9]+$ ]];
     ```
   - **Explanation**:
     - **`^`**: Ensures the pattern starts at the beginning of the input.
     - **`[0-9]+`**: Checks that the input consists of one or more digits.
     - **`$`**: Ensures the pattern ends at the end of the input.
     - The **`!`** negates the condition, so the loop will continue prompting until the input is a positive integer.

