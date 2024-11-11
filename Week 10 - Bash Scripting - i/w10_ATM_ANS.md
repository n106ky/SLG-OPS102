# ATM Exercise: Answer
```
#!/usr/bin/bash

SAVINGS=100000

read -p "\nHello! Please enter your name: " NAME
echo -e "\n\
Welcome back, $NAME.\n\n\
Which service do you need today?"

# -e to enable escape sequences
echo -e "\
1. DEPOSIT\n\
2. WITHDRAWAL\n\
3. CHECK SAVINGS ACCOUNT\n\
4. SAVINGS PLAN\n"

read -p "Select a service (1-4): " SRV

if [[ $SRV == 1 ]]
then
        echo -e "\nYou selected 1. DEPOSIT\n"

        read -p "Please enter the deposit amount (CAD\$): " AMT
        echo -e "\nYou have deposited $AMT.\nYour new balance is $(( SAVINGS + AMT )).\n"
elif [[ $SRV == 2 ]]
then
        echo -e "\nYou selected 2. WITHDRAWAL\n"

        read -p "Please enter the withdrawal amount (CAD\$): " AMT
        echo -e "\nYou have withdrawn $AMT.\nYour new balance is $(( SAVINGS - AMT )).\n"
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
```
