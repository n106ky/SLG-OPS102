
# PART A: Package Management and Related Commands

## Windows Package Management

### `winget`
Explore `winget` with the following commands:
- `winget search`
- `winget show`
- `winget install`
- `winget uninstall`

## Linux Package Management

### 1. `rpm`
Explore `rpm` with the following commands:
- `rpm -q bash` (example usage)
- Options to explore:
  - `-q`
  - `-a`
  - `-i`
  - `-f`
  - `--requires`
  - `--whatrequires`

### 2. `dnf`
Explore `dnf` with the following subcommands:
- `dnf info`
- `dnf update`
- `dnf search`


### 3. Additional Command Lines to Explore
1. `wget`
2. `tar`
3. `./configure`
4. `make`
<br>

# PART B: Install Your Version of `nano`
```bash
# Check the current nano version
nano --version

# Create a directory and download the source code
mkdir sample
cd sample
wget https://www.nano-editor.org/dist/v8/nano-8.2.tar.xz
ls  # Verify the download

# Execute the following command. What does `tar xvf` do? 
tar xvf nano-8.2.tar.xz 
cd nano-8.2
ls -l  # List detailed files

# Configure the build environment and compare outputs with the following commands 
./configure
./configure --prefix=$HOME/local

# Execute the following command. What does `make -j4` and `make install` do? 
time make -j4
ls src  # Verify the compiled files
make install 

# Compare the installed versions
~/local/bin/nano --version
nano --version
```
<br>

# PART C: Final Practice
Link to the Practice         [EXE OPS Sample Test](Week%2014%20-%20Software%20Management%20and%20Final%20Practice/Final%20Practice/EXE_OPS_Sample_Test.docx)  
Link to the Sample Answer    [ANS OPS Sample Test](Week%2014%20-%20Software%20Management%20and%20Final%20Practice/Final%20Practice/ANS_OPS_Sample_Test.docx)


