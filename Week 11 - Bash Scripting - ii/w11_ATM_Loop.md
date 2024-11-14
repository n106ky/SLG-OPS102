# Exercise: ATM Continue

## Objectives
Practice using the Matrix server (Linux) and apply what you've learned in this session to implement **loops** in a Bash script.  

**Recap 4 Types of Loops:**  
```for VARIABLE in LIST```: Iterates over items in a list.  
```for (( ; ; ))```: C-style loop, useful for specifying initialization, condition, and modification (increment / decrement).  
```while EXPR```: Loops while the condition is true.  
```until EXPR```: Loops until the condition is met.  

You may refer to [Bash Scripting - 2](http://15.223.64.81/doku.php?id=ops102:bash_scripting_2_-_loops) course materials.

---
## Step-by-Step Instructions

In this exercise, you’ll use **for-loop**, **while-loop**, and **until-loop** to create an interactive ATM program.  

### Preparation:

Connect to your matrix terminal for this practice.

If you have not completed last week's exercise, you may travel back to [Week 10 folder](https://github.com/n106ky/SLG-OPS102/blob/main/Week%2010%20-%20Bash%20Scripting%20-%20i/w10_ATM_ANS.md) and upgrade the code, or use the following code as a template or guideline.

```bash
#!/usr/bin/bash

SAVINGS=100000


# Q1 INITIALIZATION: FOR THE WHILE LOOP
CONT="Y"


read -p "Hello! Please enter your name: " NAME
echo -e "\n\
Welcome back, $NAME.\n\n\
Which service do you need today?"

# Q1. APPLY WHILE LOOP TO CHECK IF USER WANTS TO CONTINUE

        # Q2. FOR LOOP TO DISPLAY THE SERVICE ITEMS

        read -p "Select a service (1-4): " SRV

        # Q3. UNTIL-LOOP TO CHECK IF USER INPUT "SRV" IS BETWEEN 1 - 4


        if [[ $SRV == 1 ]]
        then
                echo -e "\nYou selected 1. DEPOSIT\n"

                read -p "Please enter the deposit amount (CAD\$): " AMT
                # Q4. VALIDATE IF USER INPUT A POSITIVE AMOUNT

                echo -e "\nYou have deposited $AMT.\nYour new balance is $(( SAVINGS = SAVINGS + AMT )).\n"

        elif [[ $SRV == 2 ]]
        then
                echo -e "\nYou selected 2. WITHDRAWAL\n"

                read -p "Please enter the withdrawal amount (CAD\$): " AMT

                # Q4. VALIDATE IF USER INPUT A POSITIVE AMOUNT (SAME AS ABOVE)


        echo -e "\nYou have withdrawn $AMT.\nYour new balance is $(( SAVINGS = SAVINGS - AMT )).\n"
        elif [[ $SRV == 3 ]]
        then
                echo -e "\nYou selected 3. CHECK SAVINGS ACCOUNT\n"
                echo -e "Your current balance is $SAVINGS.\n"
        else
                echo -e "\nYou selected 4. SAVINGS PLAN\n"
                echo -e "Plan details:\nYou can receive 3 times the amount after 1 year from now!\n"

                read -p "Are you sure you want to proceed (Y/N)? " ANS
                if [[ $ANS == Y || $ANS == "y" ]]
                then
                        read -p "Please enter the amount that you want to save: " AMT
                        echo -e "\nYou are saving $AMT on $(date +"%Y-%m-%d").\nOne year later, you will gain $(( NEW=$AMT * 3 )).\nYour total balance will be $(( NEW + SAVINGS )) on $(date -d "+1 year" +"%Y-%m-%d").\n"
                else
                        echo -e "\nThank you for using our service. Goodbye!\n"
                fi
        fi

        # Q1. READ USER INPUT IF THEY WANTS TO CONTINUE THE SERVICE (CONT)

        # Q5. VALIDATE USER INPUT "CONT", IT ACCEPTS ONLY (Y / y / N / n)
```

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
## Key Bash Concepts in this exercise

1. **Conditional Statements**:
   - `if...elif...else` blocks control program flow based on the user’s choices.
   - `[[]]` syntax is used for conditions, and logical operators like `||` check multiple conditions.

2. **Loops**:
   - **While-loop**: Repeats actions based on conditions, e.g., to keep the program running until the user exits.
   - **For-loop**: Iterates over a list, e.g., to display service options.
   - **Until-loop**: Repeats prompts until valid input is given, ensuring user input correctness.

3. **Regular Expressions**:
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

