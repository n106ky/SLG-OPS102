# ATM (LOOP) Exercise: ANSWER
```bash
#!/usr/bin/bash

SAVINGS=100000  # User initial saving amount
CONT="Y"        # If user wish to continue using the service

        read -p "Hello! Please enter your name: " NAME
        echo -e "\n\
        Welcome back, $NAME.\n\n\
        Which service do you need today?\n"

while [[ "$CONT" == "Y" || "$CONT" == "y" ]]
do
        # change selection list to for-loop
        for ITEM in "1. DEPOSIT" "2. WITHDRAWAL" "3. CHECK SAVINGS ACCOUNT" "4. SAVINGS PLAN"
        do
                echo "  $ITEM"
        done

        echo
        read -p "Select a service (1-4): " SRV

        until [[ "$SRV" -ge 1 && "$SRV" -le 4 ]]
        do
                read -p "Incorrect Input. Please input number 1-4: " SRV
        done

        if [[ $SRV == 1 ]]
        then
                echo -e "\nYou selected 1. DEPOSIT\n"
                read -p "Please enter the deposit amount (CAD\$): " AMT

                while [[ "$AMT" -le 0 || ! "$AMT" =~ ^[0-9]+$ ]] # =~ regular expression matching
                do
                        read -p "Please enter a postive number: " AMT
                done

                echo -e "\nYou have deposited $AMT.\nYour new balance is $(( SAVINGS = SAVINGS + AMT )).\n"

        elif [[ $SRV == 2 ]]
        then
                echo -e "\nYou selected 2. WITHDRAWAL\n"
                read -p "Please enter the withdrawal amount (CAD\$): " AMT


                while [[ "$AMT" -le 0 || ! "$AMT" =~ ^[0-9]+$ ]] # =~ regular expression matching
                do
                        read -p "Please enter a postive number: " AMT
                done

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
                        echo -e "\nThank you for considering our service!\n"
                fi
        fi

        echo    "============================================================"
        read -p "Do you wish to use another service? (Y/N): " CONT

        until [[ "$CONT" == "y" || "$CONT" == "Y" || "$CONT" == "n" || "$CONT" == "N" ]]
        do
                read -p "Please enter (Y/N): " CONT
        done

        echo
done


echo -e "Thank you for using our service!\n"
```
