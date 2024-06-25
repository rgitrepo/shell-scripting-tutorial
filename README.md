# shell-scripting-tutorial

### 1. Introduction to Bash Scripting

**What is Bash?**
Bash (Bourne Again SHell) is a shell and programming language for the GNU Operating System. It's widely used on various UNIX-like systems and is the default shell on most Linux distributions and macOS.

**Creating a Bash Script**
To start writing a Bash script, create a new text file and start with the shebang line, which tells the system which interpreter to use:

```bash
#!/bin/bash
```

Make the script executable:

```bash
chmod +x script_name.sh
```

Run the script:

```bash
./script_name.sh
```

### 2. Basic Commands and Syntax

**Echo Command**
Used to display a line of text/string:

```bash
echo "Hello, World!"
```

**Variables**
Creating and using variables:

```bash
name="Alice"
echo "Hello, $name!"
```

**Reading Input**
Reading input from the user:

```bash
read -p "Enter your name: " name
echo "Hello, $name!"
```

### 3. Conditional Statements

**If-Else Statement**
Simple if-else example:

```bash
read -p "Enter a number: " num
if [[ $num -gt 10 ]]
then
    echo "The number is greater than 10."
else
    echo "The number is 10 or less."
fi
```

### 4. Loops

**For Loop**
Loop through a list of numbers:

```bash
for i in {1..5}
do
    echo "Number $i"
done
```

**While Loop**
Condition-based looping:

```bash
count=1
while [[ $count -le 5 ]]
do
    echo "Count $count"
    ((count++))
done
```

### 5. Case Statements

Handling multiple conditions using a case statement:

```bash
read -p "Enter your choice: " choice
case $choice in
    1) echo "You chose option 1";;
    2) echo "You chose option 2";;
    *) echo "Invalid option";;
esac
```

### 6. Functions

**Creating Functions**
A simple function to display a greeting:

```bash
function greet {
    echo "Hello, $1!"
}
greet "Alice"
```

**Return Values**
Using output from a function:

```bash
function add {
    local sum=$(( $1 + $2 ))
    echo $sum
}

result=$(add 5 3)
echo "The sum is $result"
```

### 7. Advanced Topics

**Debugging**
Turn on debugging:

```bash
set -x
```

Turn off debugging:

```bash
set +x
```

**Arrays and Substrings**
Working with arrays and manipulating their content:

```bash
arr=(apple banana cherry)
echo "${arr[1]}"          # Outputs banana
echo "${arr[@]:1:2}"      # Outputs banana cherry
```

### 8. Practical Examples

**Script with Arguments**
Using positional parameters:

```bash
#!/bin/bash
echo "Script Name: $0"
echo "First Argument: $1"
echo "Second Argument: $2"
```

Run this script with two arguments to see how it handles input parameters.

This tutorial covers the basics and some advanced aspects of Bash scripting. With practice, you'll get more comfortable and discover even more functionalities of Bash.
