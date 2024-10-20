# Preparation

**1. How to Run an Ubuntu Desktop Virtual Machine Using VirtualBox**  
  - [Follow this tutorial](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview) to set up an Ubuntu Desktop virtual machine on VirtualBox.

**2. Download VirtualBox**  
  - You can download VirtualBox from [this link](https://www.virtualbox.org/wiki/Downloads).

---

# Exercise

## Exploring Group and File Permissions in Ubuntu

In this exercise, you will create a new group called `explorers`, add yourself to the group, and experiment with file ownership and permissions.

### Step 1: Create a New Group

1. Open your terminal. Print user and group IDs using `id`:  
   ```
   id
   ```
2. Create a new group called explorers:
   ```
   sudo groupadd explorers
   ```

3. Verify that the group was created by listing it in the group file using the grep command:
   ```
   grep explorers /etc/group
   ```

### Step 2: Add Yourself to the New Group
1. Add yourself to the explorers group using the usermod command. Replace $USER with your username, or use the $USER variable:
   ```
   sudo usermod -aG explorers $USER
   ```
2. To apply the group changes, either log out and log back in or use the following command to switch to the new group without logging out:
   ```
   newgrp explorers
   ```
3. Verify that you have been added to the group by running the groups command:
   ```
   groups
   ```
   You should see explorers listed as one of your groups.


### Step 3: Create and Explore File Permissions
1. Install tree (if it's not installed) and 
   ```
   sudo apt install tree
   ```

2. Create a new directory and files to work with:
   ```bash
   pwd                        # To check your current directory
   cd Desktop                 # Move to your Desktop
   mkdir Testing              # Create a new directory
   cd Testing                 # Change to the new directory
   touch file1.txt file2.txt  # Create two empty text files
   ls -l                      # List the files with their details
   ```
   
3. Change the group ownership of file1.txt to the explorers group:
   ```
   chgrp explorers file1.txt
   ```

4. Verify the group ownership change by running the ls -l command:
   ```
   ls -l
   ```
   You should see explorers listed as the group in the output. For example:
   ```
   -rw-r--r-- 1 user explorers 0 Oct 20 12:00 file1.txt
   ```
