# Exercise: ATM

## Objectives
Practice using the Matrix server (Linux) and apply what you've learned in this session to write a Bash script for this exercise.

The goal of this script is to simulate a simple ATM system with these options:
1. **Deposit** - Add money to the current account balance.
2. **Withdrawal** - Deduct money from the current account balance.
3. **Check Savings Account** - Display the current balance.
4. **Savings Plan** - Show a plan where the user can grow their balance by three times in one year.

---

## Step-by-Step Instructions

### 1. Set Initial Balance
- Define a variable to hold the **initial savings balance** (e.g., `100000`).
- This variable will represent the user’s **current account balance** and will be updated based on their actions.


### 2. Ask for User's Name
- Prompt the user to enter their name.
- Store this input in a variable (e.g., `NAME`) and use it to personalize the welcome message.


### 3. Display the Service Options and Prompt for Selection
- Use `echo` to display the list of available services, numbered 1 to 4:
    1. Deposit
    2. Withdrawal
    3. Check Savings Account
    4. Savings Plan
- Ask the user to **select a service** by entering a number (1-4).
  - Store user selection in a variable (e.g., `SRV`).

### 4. Handle Each Service Option with Conditionals

**Option 1: Deposit**
- Check if the user selected **option 1 (Deposit)**.
- If so:
    - Prompt the user to enter a **deposit amount**.
    - Add this amount to the **current balance** and display the **new balance**.

**Option 2: Withdrawal**
- Check if the user selected **option 2 (Withdrawal)**.
- If so:
    - Prompt the user to enter a **withdrawal amount**.
    - Subtract this amount from the **current balance** and display the **new balance**.
    - Optionally, consider adding **error handling** to check if the withdrawal amount is greater than the current balance.

**Option 3: Check Savings Account**
- Check if the user selected **option 3 (Check Savings Account)**.
- If so:
    - Simply display the **current balance**.
      
**Option 4: Savings Plan**
- If the user selected **option 4 (Savings Plan)**, display details of a savings plan:
    - Explain that the user can grow the pricipal by **three times** after one year.
    - Confirm with the user if they want to proceed.
        - If they answer "Y” or “y”:
            - Prompt them to enter an amount they want to save.
            - Calculate the **projected balance after one year**, showing:
                - **The date today**
                - **The date one year from today**
                - **The tripled amount** and the **total projected balance** after one year.


---
## Sample Output
**Ask for User's Name** 
**Display the Service Options and Prompt for Selection**  
<img src="https://github.com/user-attachments/assets/6db5153d-241b-4b7a-9201-cf45d32d267e" width="500">

**If user chose option 1**  
<img src="https://github.com/user-attachments/assets/a18f7c81-3828-4edd-8655-ee6725998d6b" width="500">

**If user chose option 2**  
<img src="https://github.com/user-attachments/assets/ba98fa09-1ec1-499c-b249-17d3314b0cb7" width="500">

**If user chose option 3**  
<img src="https://github.com/user-attachments/assets/b217e26e-3458-47b5-8f26-3ce4c019ea09" width="500">

**If user chose option 4**  
<img src="https://github.com/user-attachments/assets/195c3316-2e64-4950-a30c-09b09d832013" width="500">  
**or if user abort selection 4**  
<img src="https://github.com/user-attachments/assets/a4506c24-855d-45e3-aadc-0ac7866aa2e7" width="500">

---
## Key Bash Concepts

1. **Variables**:
    - Define variables for storing **initial value**, and **user input**.
2. **Input and Output**:
    - Use `read` to capture user input.
    - Use `echo` to display messages, options, and results to the user.
    - Enable escape sequences (`\\n` for newlines) in `echo` by adding the `-e` option.
3. **Conditional Statements**:
    - Use `if... then`, `elif... then`, `else`, and `fi` to handle different actions based on the user’s selection.
    - Follow the format if [[ ... ]] for conditions.
4. **Arithmetic Operations**:
    - Using **arithmetic expansion** (e.g., `$(( ... ))`) to add, subtract, or multiply amounts from the current balance.
5. **Date Commands**:
    - Use the `date` command to show the current date and to calculate a date one year from now.
    - Use `+"%Y-%m-%d"` to format dates consistently in the `YYYY-MM-DD` format.
    - Linux uses option `-d` and `"+1 year"` to get the date one year from now.
6. **Logical OR in Conditional Statements**:
    - Use `||` to check for multiple conditions. For example, if the user’s response is either "Y" or "y" (for case insensitivity), execute the next block.


