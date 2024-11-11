# Bash Scripting Course Outline

Welcome to the Bash Scripting course! This course is designed to give you a foundational understanding of bash scripting and its applications in automating tasks and managing systems. This outline provides a step-by-step guide for learning bash scripting, starting from basics to advanced topics.

---

## Table of Contents

1. **Introduction to Bash Scripting**
   - What is Bash?
   - Why Use Bash Scripting?
   - Basic Syntax and Structure of Bash Scripts
   - Running Your First Bash Script

2. **Shell Basics and Command Line Essentials**
   - Navigating the Shell: Basic Commands (ls, cd, pwd, etc.)
   - Understanding File Permissions and Ownership
   - Basic File Operations (cp, mv, rm, mkdir, etc.)
   - Working with Text Files (cat, echo, nano, vi)

3. **Variables and Data Types**
   - Declaring Variables
   - Environment vs Local Variables
   - Reading User Input with `read`
   - Special Variables ($0, $1, $#, $@)

4. **Operators and Basic Arithmetic**
   - Arithmetic Operators
   - Comparison Operators
   - String Operators
   - Logical Operators (&&, ||)

5. **Conditional Statements**
   - `if` Statements
   - `if-else` Statements
   - `elif` Statements
   - `case` Statements for Multi-condition Checks

6. **Loops in Bash**
   - `for` Loops
   - `while` Loops
   - `until` Loops
   - Using `break` and `continue`

7. **Functions in Bash**
   - Creating and Calling Functions
   - Function Parameters and Return Values
   - Scope of Variables in Functions

8. **File and Directory Management**
   - Checking Existence of Files and Directories
   - File Manipulation (Creating, Renaming, Deleting)
   - Directory Traversal and Path Manipulation

9. **Text Processing and Manipulation**
   - Using `grep`, `sed`, and `awk` for Text Processing
   - Regular Expressions Basics
   - Sorting, Searching, and Replacing Text
   - Parsing Log Files

10. **Working with Input and Output**
    - Redirecting Output (`>`, `>>`, `2>`, etc.)
    - Using Pipes to Combine Commands (`|`)
    - Using `tee` for Split Output
    - Reading Files Line by Line

11. **Error Handling and Debugging**
    - Understanding Exit Status and `$?`
    - Error Messages and Logging
    - Enabling Debug Mode (`set -x`)
    - Common Debugging Techniques

12. **Advanced Topics**
    - Script Optimization and Best Practices
    - Working with Background Jobs
    - Scheduling Scripts with `cron`
    - Using `trap` for Signal Handling
    - Introduction to `getopts` for Parsing Command-Line Options

13. **Practical Applications of Bash Scripting**
    - Automating Repetitive Tasks
    - System Administration Basics
    - File Management Automation
    - Network Operations and Monitoring
    - Real-world Scripting Examples

14. **Final Project**
    - Project Overview
    - Requirements and Guidelines
    - Additional Resources

---

Each section will include code examples, exercises, and best practices to reinforce learning. By the end of this course, you’ll be equipped to write and debug bash scripts confidently.

Happy Scripting!

# 1. Introduction to Bash Scripting

Welcome to Bash Scripting! This section will introduce you to the basics of bash, its uses, and how to create and run simple scripts. By the end of this section, you'll understand what bash scripting is and have written your first script.

---

### What is Bash?

**Bash** (Bourne Again SHell) is a command-line interpreter for Unix-based operating systems. It’s the default shell for many Linux distributions and macOS, allowing users to interact with the system by typing commands.

Bash scripting allows us to automate tasks, perform system maintenance, and create workflows, making it a powerful tool for system administrators, developers, and anyone working with Unix-based systems.

### Why Use Bash Scripting?

Bash scripting offers several benefits, including:

- **Automation**: Automate repetitive tasks like backups, system cleanups, and software installations.
- **Efficiency**: Save time by chaining multiple commands and scripts together.
- **Flexibility**: Easily customize tasks with variables, conditionals, and loops.
- **Cross-platform**: Bash scripts work on most Unix-based systems, including Linux, macOS, and WSL on Windows.

### Basic Syntax and Structure of Bash Scripts

A bash script is simply a file containing a series of commands executed in sequence. Here’s the basic syntax:

1. **Shebang Line**: The first line in a script, `#!/bin/bash`, tells the system to use bash as the interpreter.
2. **Comments**: Lines starting with `#` are comments, which help explain the script and are ignored by the shell.
3. **Commands**: Each line contains a command or an instruction for the shell to execute.

**Example Script Structure:**
```bash
#!/bin/bash
# This is a sample bash script

echo "Hello, World!"  # Prints Hello, World! to the screen
```

### Running Your First Bash Script
Follow these steps to create and run your first bash script:
1. Create the Script File:
    - Open a terminal.
    - Use touch to create a new file: touch hello_world.sh.
    - Open the file in a text editor, such as nano hello_world.sh.

2. Add Content to the Script:
    - Write the following lines in hello_world.sh:
```bash
#!/bin/bash
# My first bash script
echo "Hello, World!"
```
3. Save and Close the file.
4. Make the Script Executable:
```bash
chmod +x hello_world.sh
```
5. Run the Script:
```bash
./hello_world.sh
```
Here, you should see the output as "Hello, World!" on terminal.

#Explanation of Key Concepts
- Shebang (#!/bin/bash): The shebang line tells the system to use bash to interpret the script.
- Comments (#): Comments are used for documentation. They start with # and are ignored by the shell.
echo: 
- This command prints text to the terminal.



# 2. Shell Basics and Command Line Essentials

This section will introduce you to the shell environment, basic commands, and file manipulation in bash. Understanding these commands will provide a solid foundation for working with bash scripts and navigating the command line.

---

### What is the Shell?

The **shell** is a command-line interface that allows users to interact with the operating system by typing commands. Bash (Bourne Again SHell) is one of the most popular shells, especially on Linux and macOS. The shell interprets commands and executes them, providing feedback in the terminal.

### Navigating the Shell: Basic Commands

Below are some fundamental commands to navigate the filesystem and manage files and directories.

- **`pwd` (Print Working Directory)**:
  - Displays the current directory path.
  - **Usage**: `pwd`
  
- **`ls` (List)**:
  - Lists the contents of a directory.
  - Options:
    - `ls -l`: Lists in long format with details.
    - `ls -a`: Lists all files, including hidden files.
    - `ls -lh`: Lists with human-readable sizes.
  - **Usage**: `ls`, `ls -l`, `ls -a`
  
- **`cd` (Change Directory)**:
  - Changes the current directory.
  - Examples:
    - `cd /path/to/directory`: Moves to a specific directory.
    - `cd ..`: Moves up one level in the directory tree.
    - `cd ~`: Moves to the home directory.
  - **Usage**: `cd directory_name`

### Understanding File Permissions and Ownership

Every file in Linux has **permissions** and an **owner**. File permissions control who can read, write, or execute a file.

- **Permission Types**:
  - `r` (Read): Allows viewing the file's contents.
  - `w` (Write): Allows modifying the file.
  - `x` (Execute): Allows running the file as a program.

- **Viewing Permissions**:
  - Use `ls -l` to see the permissions for each file.
  - Example output: `-rwxr-xr--`
    - The first character represents the file type (`-` for file, `d` for directory).
    - The next three characters are permissions for the **owner**.
    - The following three characters are for the **group**.
    - The last three characters are for **others**.

- **Changing Permissions**:
  - Use `chmod` to modify permissions.
  - Examples:
    - `chmod +x file`: Adds execute permission.
    - `chmod 755 file`: Sets specific permissions (owner: read, write, execute; group: read, execute; others: read, execute).

### Basic File Operations

These commands help you create, move, and delete files and directories:

- **`touch`**: Creates an empty file.
  - **Usage**: `touch filename`
  
- **`cp` (Copy)**:
  - Copies files or directories.
  - Options:
    - `cp -r`: Recursively copies directories.
  - **Usage**: `cp source destination`, `cp -r dir1 dir2`
  
- **`mv` (Move/Rename)**:
  - Moves or renames files and directories.
  - **Usage**: `mv old_name new_name`, `mv file /path/to/destination`

- **`rm` (Remove)**:
  - Deletes files or directories.
  - Options:
    - `rm -r`: Recursively deletes directories.
    - `rm -i`: Prompts before each deletion.
  - **Usage**: `rm file`, `rm -r directory`

- **`mkdir` (Make Directory)**:
  - Creates a new directory.
  - **Usage**: `mkdir directory_name`
  
### Working with Text Files

Bash offers several commands for viewing and manipulating text files directly from the terminal:

- **`cat`**: Displays the contents of a file.
  - **Usage**: `cat filename`
  
- **`echo`**: Prints text to the screen or writes text to a file.
  - **Usage**: `echo "Hello, World!"`, `echo "Hello" > file.txt`
  
- **`nano` and `vi`**: Text editors for creating or editing files.
  - **nano**: Easy-to-use, beginner-friendly editor.
  - **vi**: A more advanced, powerful text editor with multiple modes.
  - **Usage**: `nano filename`, `vi filename`

---

### Practice Exercise

Try these steps to practice basic shell commands:

1. Use `pwd` to confirm your current directory.
2. Create a directory named `test_directory` using `mkdir`.
3. Navigate into `test_directory` with `cd`.
4. Create an empty file named `example.txt` using `touch`.
5. List files in `test_directory` using `ls`.
6. Rename `example.txt` to `sample.txt` using `mv`.
7. Add text to `sample.txt` by running `echo "Hello, Bash!" > sample.txt`.
8. View the contents of `sample.txt` using `cat`.
9. Go back to the parent directory with `cd ..`.
10. Remove `test_directory` and its contents using `rm -r test_directory`.

---

Mastering these essential commands will make it easier to work with files, directories, and the command line environment in bash scripts. In the next section, we’ll cover **variables and data types** to enhance script flexibility.

# 3. Variables and Data Types

Variables are essential in bash scripting, allowing you to store, manipulate, and retrieve data. In this section, we’ll cover how to declare variables, work with different types of data, and read user input.

---

### Declaring Variables

In bash, variables do not require explicit data type declarations. They are typically strings by default, but bash interprets them as needed.

- **Syntax**:
```bash
  variable_name="value"
```
Example:
```bash
name="Alice"
echo $name  # Output: Alice
```

Rules:
- Variable names should start with a letter or underscore.
- Avoid spaces around the = sign (e.g., name = "Alice" will cause an error).
- Use $variable_name to retrieve the variable's value.


### Environment vs. Local Variables
**Local Variables**:- Defined within a script or session and available only in that context.
example:
```bash
local_variable="I am local"
echo $local_variable
```
**Environment Variables**:
    - Available globally across all shells and scripts.
    - Set using export, making them accessible to other scripts and processes.

Example:
```bash
export PATH="/usr/local/bin:$PATH"
echo $PATH
```

### Reading User Input with read
The read command is used to get user input and store it in a variable.
syntax:
```
read variable_name
```

- Prompting user
```bash
echo "Enter your name:"
read name
echo "Hello, $name!"
```

-p: Prompt the user without echo.

-s: Hide input (useful for passwords).

Example with -p
```bash
read -p "Enter your favorite color: " color
echo "You chose $color."
```

### Special Variables
Bash provides several special variables with predefined meanings, often used in scripts to handle parameters and metadata.
```bash
$0: The name of the script.
$1, $2, ...: Positional parameters (arguments passed to the script).
$#: The number of positional parameters.
$@: All positional parameters (arguments) as a single string.
$?: The exit status of the last executed command.
$$: The process ID of the current shell.
```

Example:
```bash
#!/bin/bash
echo "Script name: $0"
echo "First argument: $1"
echo "All arguments: $@"
echo "Total arguments: $#"
```

### Types of Data in Bash
Bash treats all variables as strings by default, but it also allows numerical operations and arrays. Below are common data types you’ll encounter in bash.

1. Strings
- Strings are sequences of characters.
- Defined using quotes (either single ' or double ").

Example:
```bash
greeting="Hello, World"
echo $greeting
```

2. Numbers (Integers)
- Bash supports basic integer arithmetic.
- To perform calculations, you can use expr, $(( ... )), or let.

Example:
```bash
num1=10
num2=5
sum=$((num1 + num2))
echo "Sum: $sum"
```
3. Arrays
- Arrays store multiple values in a single variable.

- Use parentheses to define an array and access elements with an index starting from 0.

- Example:
```bash
fruits=("apple" "banana" "cherry")
echo ${fruits[0]}  # Output: apple
echo ${fruits[@]}  # Output: apple banana cherry
```
- Modifying Arrays:
    - Add a value: fruits[3]="orange"
    - Remove a value: unset fruits[1]

```bash
## Practice Exercise
1. Define and Print Variables:

- Define variables for your name, age, and favorite color.
- Print each value with descriptive text (e.g., "My name is...").
2. Create an Interactive Script:

- Prompt the user for their first name and favorite hobby.
- Display a message like "Hello, [name]! It’s great that you enjoy [hobby]."
3. Use Special Variables:

- Create a script that takes three arguments and prints each one.
- Print the total number of arguments passed.
4. Calculate and Print:

- Define two numbers as variables.
- Calculate and print their sum, difference, and product.
```


# 4. Operators and Basic Arithmetic

In bash scripting, operators are used to perform arithmetic calculations, comparisons, and logical operations. This section covers different types of operators and how to use them in your scripts.

---

### Arithmetic Operators

Bash provides several operators for basic arithmetic operations, which are commonly used in scripts for calculations.

- **Syntax**:
  - Use `$(( expression ))` for arithmetic operations.
  - Example:
    ```bash
    result=$((5 + 3))
    echo $result  # Output: 8
    ```

- **Common Arithmetic Operators**:
  - `+` : Addition
  - `-` : Subtraction
  - `*` : Multiplication (use `\*` when outside `$(( ))`)
  - `/` : Division (returns the integer part of the result)
  - `%` : Modulus (remainder of division)
  - `**` : Exponentiation (not supported in all bash versions; use with `bc` for floating points)

**Example: Basic Arithmetic Operations**
```bash
a=10
b=3
echo "Addition: $((a + b))"
echo "Subtraction: $((a - b))"
echo "Multiplication: $((a * b))"
echo "Division: $((a / b))"
echo "Modulus: $((a % b))"
```
### Comparison Operators
Comparison operators are used in conditional statements to compare values. These operators typically return 0 (true) or 1 (false).
```bash
- Integer Comparison:
  -eq : Equal to
  -ne : Not equal to
  -gt : Greater than
  -ge : Greater than or equal to
  -lt : Less than
  -le : Less than or equal to
```
Example:
```bash
x=10
y=20
if [ $x -lt $y ]; then
  echo "$x is less than $y"
fi
```

- String Comparison:
```
- = : Equal to
- != : Not equal to
- < : Less than (alphabetical order)
- > : Greater than (alphabetical order)
```

Example:
```bash
str1="apple"
str2="banana"
if [ "$str1" \< "$str2" ]; then
  echo "$str1 comes before $str2"
fi
```

### String Operators
String operators are used to perform checks on strings, such as checking their length or content.
```bash
### Common String Operators:

-z : True if the string is empty.
-n : True if the string is not empty.
= : True if two strings are equal.
!= : True if two strings are not equal.
```

Example:
```bash
name="Alice"
if [ -n "$name" ]; then
  echo "The variable 'name' is not empty"
fi
```
### Logical Operators
Logical operators combine multiple conditions. They are especially useful in if statements and loops.
- Common Logical Operators:
```bash
&& : Logical AND (both conditions must be true)
|| : Logical OR (at least one condition must be true)
! : Logical NOT (inverts the condition)
```
Example:
```bash
age=25
if [ $age -gt 18 ] && [ $age -lt 30 ]; then
  echo "You are in your twenties"
fi
```

### Performing Arithmetic with expr
The expr command is another way to perform arithmetic operations, though it’s less commonly used in modern bash scripts. Each operator must be separated by spaces.
```bash
sum=$(expr 5 + 3)
echo "Sum: $sum"
```

### Advanced Arithmetic with bc
For more complex calculations, especially involving floating-point numbers, you can use the bc (Basic Calculator) tool.

- Example with Floating-Point Division:
```bash
result=$(echo "scale=2; 10 / 3" | bc)
echo $result  # Output: 3.33
```

### Practice Exercise
```bash

1. Basic Calculations:

- Define two variables, num1 and num2, with integer values.
- Perform addition, subtraction, multiplication, division, and modulus on these variables and print each result.
2. Comparison:

- Write a script that accepts two numbers as arguments.
- Check if the first number is greater than, less than, or equal to the second number.
3. Logic and String Comparison:

- Prompt the user to enter their age.
- Use logical operators to check if the age is between 18 and 65 and print a message like "You are eligible" if true.
4. Using bc for Advanced Calculations:

- Write a script that calculates the square root of a number using bc.
- Example: echo "scale=2; sqrt(25)" | bc should output 5.00.
```


# 5. Conditional Statements

Conditional statements allow your scripts to make decisions based on certain conditions. Bash provides several ways to write conditionals, including `if` statements, `case` statements, and ternary-like operations. This section explains how to use these statements to control the flow of your scripts.

---

### `if` Statement

The `if` statement is used to execute commands based on whether a condition is true. 

- **Basic Syntax**:
```bash
  if [ condition ]; then
    # Commands to execute if condition is true
  fi
```

Example:
```bash
number=10
if [ $number -gt 5 ]; then
  echo "$number is greater than 5"
fi
```
- Using else and elif:

  - You can add an else block to specify commands if the condition is false.
  - elif allows multiple conditions to be checked in sequence.

```bash
age=20
if [ $age -lt 13 ]; then
  echo "Child"
elif [ $age -lt 20 ]; then
  echo "Teenager"
else
  echo "Adult"
fi
```
### if Conditions with Multiple Tests
Use && and || operators to combine multiple conditions.

### - AND Condition (&&):
```bash
if [ $age -ge 18 ] && [ $age -le 65 ]; then
  echo "Eligible for employment"
fi
```

### - OR Condition (||)
```bash
if [ $age -lt 18 ] || [ $age -gt 65 ]; then
  echo "Not eligible for employment"
fi
```
### - case Statement
The case statement is used for multi-branch decisions and is especially useful when you have multiple possible values for a variable.
- syntax
```bash
case variable in
  pattern1)
    # Commands for pattern1
    ;;
  pattern2)
    # Commands for pattern2
    ;;
  *)
    # Commands if no patterns match
    ;;
esac
```

Example:
```bash
day="Monday"
case $day in
  "Monday"|"Tuesday"|"Wednesday"|"Thursday"|"Friday")
    echo "It's a weekday"
    ;;
  "Saturday"|"Sunday")
    echo "It's the weekend"
    ;;
  *)
    echo "Unknown day"
    ;;
esac
```
### Ternary-like Operations with && and ||
Bash doesn’t have a traditional ternary operator like in some other languages, but you can achieve similar behavior using && and ||.
- Syntax:
```bash
condition && command_if_true || command_if_false
```
Example:
```bash
age=18
[ $age -ge 18 ] && echo "Adult" || echo "Not an adult"
```
### Nested Conditionals
You can nest if statements to check multiple conditions. Be cautious with indentation to maintain readability.
Example:
```bash
num=15
if [ $num -gt 10 ]; then
  if [ $num -lt 20 ]; then
    echo "$num is between 10 and 20"
  fi
fi
```
#### Practice Excercise
```bash
1. Simple if and else:

- Write a script that accepts a number as input.
- If the number is positive, print "Positive Number"; otherwise, print "Non-Positive Number".
2. Using elif for Ranges:

- Write a script that asks the user for their age.
- Print "Child" if age < 13, "Teen" if 13 <= age < 18, and "Adult" if age >= 18.
3. Multiple Conditions with case:

- Write a script that accepts a single letter from the user (a, b, c).
- Use a case statement to print a message for each letter (e.g., "You entered A").
4. Ternary-like Operation:

- Define a variable temp with a numeric value.
- Use a ternary-like operation to print "Hot" if temp is greater than 30, or "Cool" otherwise.
```


# 6. Loops in Bash

Loops allow you to execute a block of code multiple times, which is useful for automating repetitive tasks. Bash provides several types of loops, including `for`, `while`, and `until` loops. This section covers each loop type, with examples to illustrate their usage.

---

### `for` Loop

The `for` loop iterates over a list of values, executing a set of commands for each item in the list.

- **Syntax**:
```bash
  for variable in list; do
    # Commands to execute for each item in list
  done
```

- Example: Looping over a list of words
```bash
for color in red blue green; do
  echo "Color: $color"
done
```

- Example: Looping over a sequence of numbers
```bash
for i in {1..5}; do
  echo "Number: $i"
done
```

- Example: Using for loop with C-style syntax
```bash
for ((i=1; i<=5; i++)); do
  echo "Count: $i"
done
```
### while Loop
The while loop repeatedly executes commands as long as a specified condition is true.
- Syntax:
```bash
while [ condition ]; do
  # Commands to execute as long as condition is true
done
```
- Example: Countdown loop
```bash
count=5
while [ $count -gt 0 ]; do
  echo "Count: $count"
  count=$((count - 1))
done
```
- Example: Reading user input in a loop
```bash
while true; do
  read -p "Enter a number (0 to exit): " num
  if [ $num -eq 0 ]; then
    break
  fi
  echo "You entered: $num"
done
```
### until Loop
The until loop is similar to the while loop, but it executes commands as long as the condition is false. It stops when the condition becomes true.
- Syntax
```bash
until [ condition ]; do
  # Commands to execute as long as condition is false
done
```
- Example: Incrementing until a condition is met
```bash
num=1
until [ $num -gt 5 ]; do
  echo "Number: $num"
  num=$((num + 1))
done
```

### break and continue Statements
- **break**: Exits the loop immediately, skipping any remaining commands.
Example:
```bash
for i in {1..10}; do
  if [ $i -eq 5 ]; then
    break
  fi
  echo "Number: $i"
done
```
- **continue**: Skips the current iteration and proceeds to the next iteration.
Example:
```bash
for i in {1..5}; do
  if [ $i -eq 3 ]; then
    continue
  fi
  echo "Number: $i"
done
```

### Looping Through Files and Directories
Bash loops are also useful for working with files and directories.
- Example: Listing files in a directory
```bash
for file in /path/to/directory/*; do
  echo "File: $file"
done
```
- Example: Reading lines from a file
```bash
while IFS= read -r line; do
  echo "Line: $line"
done < filename.txt
```
### Practice Exercise
```bash
1. Basic for Loop:

- Write a for loop that prints numbers 1 through 10.
2. Countdown with while Loop:

- Create a while loop that counts down from 10 to 1 and then prints "Liftoff!"
3. Using until Loop:

- Write an until loop that keeps asking the user to guess a number until they enter 7.
4. Looping Through Files:

- Write a script that lists all .txt files in a specified directory.
5. Break and Continue:

- Create a for loop that prints numbers 1 to 10.
- Skip the number 5 using continue and stop the loop when it reaches 8 using break.
```

