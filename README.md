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

# 7. Functions in Bash

Functions in Bash allow you to encapsulate and reuse blocks of code. They help organize scripts, make them more readable, and reduce redundancy. In this section, we'll cover the basics of creating and using functions, passing parameters, and using return values.

---

### Defining a Function

A function in Bash is defined with a name followed by a set of commands inside curly braces `{ }`. Function definitions must appear before they are called in the script.

- **Syntax**:
```bash
  function_name() {
    # Commands to execute
  }
```
- Example
```bash
greet() {
  echo "Hello, welcome to Bash scripting!"
}

# Call the function
greet
```
### Function Parameters
You can pass arguments to a function, and they are accessed using positional parameters within the function (e.g., $1, $2, ...).

- Example: Passing parameters to a function
```bash
greet_person() {
  echo "Hello, $1!"
}

# Call the function with an argument
greet_person "Alice"
```

- Example with Multiple Parameters:
```bash
add_numbers() {
  sum=$(( $1 + $2 ))
  echo "The sum of $1 and $2 is: $sum"
}

# Call the function with two arguments
add_numbers 3 7
```

### Returning Values from Functions
Bash functions can return a value using the return command. However, this value is limited to integers between 0 and 255 (useful for status codes). For more complex outputs, use echo or global variables.
- Using return for Status Codes:
```bash
check_even() {
  if (( $1 % 2 == 0 )); then
    return 0  # Success
  else
    return 1  # Failure
  fi
}

check_even 4
if [ $? -eq 0 ]; then
  echo "Number is even."
else
  echo "Number is odd."
fi
```

- Using echo for Value Return:
```bash
calculate_square() {
  echo $(( $1 * $1 ))
}

# Capture the output of the function
result=$(calculate_square 5)
echo "The square is: $result"
```
### Local Variables in Functions
To avoid conflicts with variables outside a function, you can use the local keyword to declare variables that are only accessible within the function.
Example:
```bash
calculate_sum() {
  local a=$1
  local b=$2
  local sum=$(( a + b ))
  echo $sum
}

# The variable `sum` is local to the function
result=$(calculate_sum 10 20)
echo "Sum: $result"
```
### Recursive Functions
A function can call itself, creating a recursive function. Be cautious with recursion in Bash, as it may lead to stack overflow if there’s no termination condition.
- Example: Factorial calculation using recursion
```bash
factorial() {
  if [ $1 -le 1 ]; then
    echo 1
  else
    previous=$(factorial $(( $1 - 1 )))
    echo $(( $1 * previous ))
  fi
}

result=$(factorial 5)
echo "Factorial of 5 is: $result"
```

### Practice Exercise
```bash
1. Simple Greeting Function:

- Write a function that accepts a name as a parameter and prints "Hello, [name]!".
2. Addition Function:

- Write a function that takes two numbers as parameters, adds them, and returns the result.
3. Even or Odd Check:

- Write a function that checks if a given number is even or odd and returns an appropriate message.
4.Using Local Variables:

- Write a function that calculates the area of a rectangle using local variables for length and width.
5.Recursive Factorial Function:

- Write a recursive function that calculates the factorial of a given number.
```

# 8. File and Directory Management

Managing files and directories is a key part of shell scripting, allowing you to automate tasks like file creation, deletion, copying, and renaming. This section covers the essential commands for handling files and directories in Bash.

---

### Creating Files and Directories

- **Creating a File**:
  - Use `touch` to create an empty file.
  - Example:
    ```bash
    touch myfile.txt
    ```

- **Creating a Directory**:
  - Use `mkdir` to create a new directory.
  - Example:
    ```bash
    mkdir mydirectory
    ```

- **Creating Nested Directories**:
  - Use the `-p` option with `mkdir` to create nested directories in one command.
  - Example:
    ```bash
    mkdir -p mydirectory/subdirectory
    ```

### Copying Files and Directories

- **Copying a File**:
  - Use `cp` to copy files.
  - Example:
    ```bash
    cp source.txt destination.txt
    ```

- **Copying a Directory**:
  - Use the `-r` (recursive) option with `cp` to copy an entire directory.
  - Example:
    ```bash
    cp -r sourcedir targetdir
    ```

### Moving and Renaming Files and Directories

- **Moving a File**:
  - Use `mv` to move a file to a different directory.
  - Example:
    ```bash
    mv myfile.txt /path/to/destination/
    ```

- **Renaming a File or Directory**:
  - Use `mv` to rename a file or directory.
  - Example:
    ```bash
    mv oldname.txt newname.txt
    ```

### Deleting Files and Directories

- **Deleting a File**:
  - Use `rm` to remove a file.
  - Example:
    ```bash
    rm myfile.txt
    ```

- **Deleting a Directory**:
  - Use `rm -r` to remove a directory and its contents.
  - Example:
    ```bash
    rm -r mydirectory
    ```

- **Forcing Deletion**:
  - Use `rm -rf` to delete files or directories without prompting, even if they’re write-protected.
  - **Caution**: This command is powerful and should be used carefully to avoid accidental data loss.
  - Example:
    ```bash
    rm -rf mydirectory
    ```

### Checking File and Directory Existence

- **Check if a File Exists**:
```bash
  if [ -f "myfile.txt" ]; then
    echo "File exists."
  else
    echo "File does not exist."
  fi
```
- Check if a Directory Exists:
```bash
if [ -d "mydirectory" ]; then
  echo "Directory exists."
else
  echo "Directory does not exist."
fi
```

### Reading from and Writing to Files
- Appending Text to a File:
  - Use >> to append text to a file.
```bash
echo "This is a new line" >> myfile.txt
```
- Overwriting Text in a File:
  - Use > to overwrite the contents of a file.
```bash
echo "This will replace existing content" > myfile.txt
```
- Reading a File Line by Line:
  - Use while loop and read command to read a file line by line.
  - Example
```bash
while IFS= read -r line; do
  echo "$line"
done < myfile.txt
```

### File Permissions
- Changing File Permissions:
  - Use chmod to modify file permissions.
  - Example:
```bash
chmod +x myscript.sh
```
- Changing File Ownership:
  - Use chown to change the owner of a file (requires root privileges).
  - Example
```bash
sudo chown user:group myfile.txt
```
```bash
### Practice Exercise
1. Create and Copy Files:

- Create a file called testfile.txt and copy it to a directory called backup.
2. Move and Rename Files:

- Write a script to create a file data.txt, then rename it to data_backup.txt.
3. Check Existence and Delete:

- Write a script that checks if a directory called old_files exists. If it does, delete it.
4. Write and Append to Files:

- Write a script that creates a file called logfile.txt, writes "Start of log" to it, and then appends a new timestamped entry each time the script is run.
5. File Permissions:

- Create a script file, make it executable, and run it.
```

# 9. Text Processing and Manipulation

Bash provides powerful tools for processing and manipulating text, which is especially useful for data extraction, formatting, and reporting. This section covers essential text-processing commands, including `cat`, `grep`, `awk`, `sed`, and more.

---

### Viewing and Displaying Text

- **`cat`**: Displays the contents of a file.
```bash
  cat filename.txt
```
- head and tail: Display the beginning or end of a file.
  - head: Shows the first few lines (default: 10 lines).
```bash
head filename.txt
head -n 5 filename.txt  # Shows first 5 lines
```
- tail: Shows the last few lines (default: 10 lines).
```bash
tail filename.txt
tail -n 5 filename.txt  # Shows last 5 lines
```

- less: Allows you to scroll through a file.
```bash
less filename.txt
```

### Searching Text with grep
- grep searches for patterns in text files, making it useful for filtering and finding specific lines of text.
  - Basic Syntax:
```bash
grep "pattern" filename.txt
```
- Examples:
  - Search for the word "error" in logfile.txt.
```bash
grep "error" logfile.txt
```
- Use the -i option for case-insensitive search.
```bash
grep -i "error" logfile.txt
```
- Search recursively in all files within a directory.
```bash
grep -r "pattern" /path/to/directory
```

### Modifying Text with sed
sed (Stream Editor) is used for text substitution, deletion, and more complex text manipulation.
- Basic Substitution:
  - Replace the first occurrence of "old" with "new" in each line.
```bash
sed 's/old/new/' filename.txt
```
  - Replace all occurrences of "old" with "new" in each line.
```
sed 's/old/new/g' filename.txt
```
- Deleting Lines:
  - Delete lines that contain a specific pattern
```bash
sed '/pattern/d' filename.txt
```
- In-Place Editing:
  - Use -i to modify the file directly (use with caution)
```bash
sed -i 's/old/new/g' filename.txt
```

### Text Processing with awk
awk is a powerful text-processing tool that splits text by columns, applies conditions, and performs complex formatting.
- **Basic Syntax:**
```bash
awk 'pattern { action }' filename.txt
```
- Example:
  - Print the first column of each line.
```bash
awk '{print $1}' filename.txt
```
  - Print lines where the third column is greater than 100.
```bash
awk '$3 > 100' filename.txt
```
  - Calculate the sum of the values in the second column.
```bash
awk '{sum += $2} END {print sum}' filename.txt
```

### Counting Words and Lines
- wc: Counts lines, words, and characters in files
  - Count lines, words, and characters
```bash
wc filename.txt
```
  - Count only lines
```bash
wc -l filename.txt
```
### Sorting and Uniqueness
- sort: Sorts lines in a file.
```bash
sort filename.txt
```
- uniq: Removes duplicate lines from a sorted file. Use with sort to ensure duplicates are adjacent.
```bash
sort filename.txt | uniq
```
- uniq -c: Counts occurrences of each unique line.
```bash
sort filename.txt | uniq -c
```

### Advanced Text Processing: cut and paste
- cut: Extracts specific fields or columns from text.
  - Extract the first and third columns (fields).
```bash
cut -d ',' -f 1,3 filename.csv
```
- paste: Merges lines from multiple files
```bash
paste file1.txt file2.txt
```

```bash
### Practice Exercise
1. Finding Patterns:

- Use grep to find all lines containing "error" in a log file and save the results to error_logs.txt.
2. Replacing Text:

- Use sed to replace all instances of "foo" with "bar" in a file called data.txt.
3. Extracting Columns with awk:

- Write a script to print the second column of data.csv where the value in the first column is greater than 50.
4. Counting and Sorting:

- Write a script that counts the number of occurrences of each word in article.txt and displays them in descending order.
5. Using cut to Extract Data:

- Use cut to extract the first and last names from a CSV file called employees.csv, where names are in the first two columns.

```

# 10. Working with Input and Output

Handling input and output effectively is fundamental to building interactive and dynamic Bash scripts. In this section, we’ll explore how to accept user input, redirect output, and work with standard input, output, and error streams.

---

### User Input with `read`

The `read` command is used to prompt the user for input during script execution.

- **Basic Syntax**:
```bash
  read variable_name
```
- Example: Prompting for user input
```
echo "Enter your name:"
read name
echo "Hello, $name!"
```
- Using -p option: To display a prompt on the same line
```bash
read -p "Enter your age: " age
echo "You are $age years old."
```
- Using -s option: To hide input (useful for passwords)
```bash
read -s -p "Enter your password: " password
echo -e "\nPassword saved securely."
```

### Command-Line Arguments
Bash scripts can accept arguments passed during execution, accessible via positional parameters.
- Accessing Positional Parameters:
  - $1, $2, ... for specific arguments.
  - $@ for all arguments as a list.
  - $# for the number of arguments.
- Example:
```bash
# Save this as example.sh
echo "First argument: $1"
echo "Second argument: $2"
echo "All arguments: $@"
echo "Number of arguments: $#"

# Run the script
# ./example.sh arg1 arg2
```

### Redirection Operators
Redirection operators control where input and output go, allowing you to save command output to files or combine output streams.
- Standard Output (> and >>):
  - `>` overwrites a file with command output.
  - `>>` appends command output to a file.
  - Example:
```bash
echo "This is a test" > output.txt     # Overwrites output.txt
echo "Another line" >> output.txt      # Appends to output.txt
```
- Standard Input (<):
  - Redirects a file as input to a command.
  - Example:
```bash
while read line; do
  echo "$line"
done < input.txt
```
- Standard Error (2>):
  - Redirects error messages to a file.
  - example
```bash
ls nonexistent_file 2> error_log.txt
```
- **Redirecting Both Standard Output and Error (&>):**
  - Redirects both standard output and error to the same file.
  - Example
```bash
command &> output_and_errors.txt
```

### Pipes (|)
Pipes take the output of one command and use it as input for another command, enabling command chaining.
- Example: Find the word "error" in a log file and display only unique lines
```bash
grep "error" logfile.txt | sort | uniq
```

### tee Command
The tee command reads from standard input and writes to both standard output and one or more files, useful for logging while displaying output.
- Example: Display command output and write it to output.log at the same time
```bash
echo "Saving this output" | tee output.log
```
- Appending with -a option:
```bash
echo "Appending to log" | tee -a output.log
```
### Here Documents (<<)
A Here Document allows you to use multi-line strings as input, typically for feeding commands.
- Syntax
```bash
command <<EOF
text
EOF
```
- Example
```bash
cat <<EOF
This is a multi-line
string input for the
cat command.
EOF
```
### Here Strings (<<<)
A Here String redirects a single string as input to a command.
- Example
```bash
grep "word" <<< "This is a sample line containing word."
```

```bash
### Practice Exercise
1. User Input and Redirection:

- Write a script that prompts the user for a filename, then appends the current date and time to that file.
2. Command-Line Arguments:

- Create a script that accepts three arguments, adds them as numbers, and outputs the sum.
3. Output Redirection and Error Handling:

- Write a script that attempts to delete a file. If the file doesn’t exist, redirect the error to error_log.txt.
4. Pipe and tee Command:

- Write a script that displays a sorted list of unique words in a file and also saves the list to unique_words.txt.
5. Here Document Usage:

- Create a script that outputs a multi-line welcome message to the user using a Here Document.
```

# 11. Error Handling and Debugging

Effective error handling and debugging are crucial for building reliable Bash scripts. This section covers techniques to handle errors gracefully, debug scripts, and ensure smooth script execution.

---

### Basic Error Handling

1. **Exit Status**:
   - Each command in Bash returns an exit status (0 for success, non-zero for errors).
   - Check the exit status of the last command using `$?`.
   - Example:
     ```bash
     ls /nonexistent_directory
     if [ $? -ne 0 ]; then
       echo "Error: Directory does not exist."
     fi
     ```

2. **`exit` Command**:
   - Exits a script immediately with a specified status code.
   - Example:
     ```bash
     echo "Exiting with error status 1."
     exit 1
     ```

3. **`||` Operator**:
   - Run a command if the previous command fails.
   - Example:
     ```bash
     mkdir mydir || echo "Failed to create directory."
     ```

4. **`&&` Operator**:
   - Run a command only if the previous command succeeds.
   - Example:
     ```bash
     cd mydir && echo "Directory changed successfully."
     ```

### Advanced Error Handling

1. **Using `set` for Error Management**:
   - `set -e`: Stops the script if any command fails (useful in critical scripts).
   - `set -u`: Treats unset variables as errors.
   - `set -o pipefail`: Ensures pipeline errors are caught.
   - Example:
     ```bash
     set -euo pipefail
     ```

2. **`trap` Command**:
   - Executes a command when the script exits or receives a signal.
   - Example: Clean up temporary files on exit.
     ```bash
     trap 'rm -f /tmp/tempfile' EXIT
     ```

3. **Custom Error Messages**:
   - Use functions to print error messages and exit.
   - Example:
     ```bash
     error_exit() {
       echo "$1" 1>&2
       exit 1
     }

     ls /nonexistent || error_exit "File not found!"
     ```

### Debugging Techniques

1. **Enabling Debug Mode**:
   - Run a script in debug mode to see each command executed.
   - **Using `-x`**:
     ```bash
     bash -x script.sh
     ```
   - Or, add `set -x` at the beginning of the script to enable debugging for specific sections.

2. **Disabling Debug Mode**:
   - Use `set +x` to turn off debugging.
   - Example:
     ```bash
     set -x   # Enable debug mode
     echo "Debugging this command"
     set +x   # Disable debug mode
     ```

3. **Printing Variable Values**:
   - Use `echo` or `printf` to print variable values for debugging.
   - Example:
     ```bash
     echo "Variable value: $myvar"
     ```

4. **Using `trap` for Debugging**:
   - Execute a command before each command runs by using `trap` with the `DEBUG` signal.
   - Example:
     ```bash
     trap 'echo "Executing: $BASH_COMMAND"' DEBUG
     ```

5. **Conditional Logging**:
   - Log messages at specific points in the script, especially within conditional checks.
   - Example:
     ```bash
     if [ -f "importantfile.txt" ]; then
       echo "File exists."
     else
       echo "Error: File missing." >> error_log.txt
     fi
     ```

### Error Logging

- Redirect error messages to a log file using `2>`.
  - Example:
    ```bash
    command 2>> error_log.txt
    ```

- Log both standard output and error with `&>`.
  - Example:
    ```bash
    mycommand &> full_log.txt
    ```

### Testing and Troubleshooting Tips

1. **Start Small**:
   - Test individual commands before combining them into a full script.

2. **Use Temporary Files**:
   - Store intermediate results in temporary files for complex scripts.
   - Example:
     ```bash
     command > /tmp/output.txt
     ```

3. **Break Down Complex Commands**:
   - Split commands over multiple lines or use subshells to isolate logic.
   - Example:
     ```bash
     ( command1 && command2 ) || echo "An error occurred."
     ```

---

### Practice Exercise

1. **Error Handling with `trap`**:
   - Write a script that creates a temporary file and deletes it on exit using `trap`.

2. **Debug Mode**:
   - Write a script with an intentional error, then run it in debug mode to identify the issue.

3. **Custom Error Messages**:
   - Create a function that checks if a file exists. If not, it should print a custom error message and exit.

4. **Exit Status Check**:
   - Write a script that attempts to copy a file. If the copy fails, it should log an error message with the date and time.

---

# 12. Advanced Topics

After mastering the basics of Bash scripting, it’s helpful to explore advanced concepts that add sophistication and flexibility to your scripts. This section covers advanced topics such as regular expressions, parallel processing, subshells, process management, and more.

---

### 1. Regular Expressions

Regular expressions (regex) are used for pattern matching, making them powerful tools for text processing.

- **Basic Usage with `grep`**:
```bash
  grep -E "pattern" filename.txt
```
- Common Regex Patterns:
```bash
^ – Matches the beginning of a line.
$ – Matches the end of a line.
. – Matches any single character.
[abc] – Matches any character in the brackets.
* – Matches zero or more occurrences of the preceding character.
+ – Matches one or more occurrences of the preceding character.
\d – Matches any digit (when using grep -P for Perl syntax).
```

- Example:
```bash
# Find lines that start with a digit
grep -E "^[0-9]" filename.txt
```
### 2. Subshells and Command Substitution
Subshells allow you to run commands in an isolated environment, making it easy to execute commands without affecting the main shell environment.
- Basic Subshell Syntax:
```bash
(command1; command2)
```
- Example
```bash
(cd /tmp && ls)
echo "Current directory: $(pwd)"  # Directory remains unchanged
```
- Command Substitution:
  - Run a command and store its output in a variable.
```bash
result=$(ls /tmp)
echo "$result"
```
### 3. Parallel Processing
Parallel processing improves performance by running multiple tasks simultaneously.
- **Using &**
  - Append & to a command to run it in the background
```bash
command1 &
command2 &
wait  # Waits for all background jobs to complete
```
- Using xargs for Parallel Execution:
```bash
cat filelist.txt | xargs -n 1 -P 4 command
```
- -n specifies the number of arguments per command, and -P sets the number of parallel jobs.
### 4. Process Management
Manage running processes to control the flow and resource usage of scripts.
- Background Jobs:
  - Run a command in the background using & and manage it with jobs, fg, and bg.
```bash
command &
jobs     # List background jobs
fg %1    # Bring job 1 to the foreground
```

- Killing Processes:
  - Use kill to terminate a process by PID.
```bash
kill -9 <pid>
```

### 5. Arrays in Bash
Arrays allow you to store multiple values in a single variable.
  - Declaring an Array:
```bash
my_array=(value1 value2 value3)
```
  - Accessing elements
``bash
echo ${my_array[0]}  # Outputs 'value1'
```
  - Looping through Arrays:
```bash
for item in "${my_array[@]}"; do
  echo "$item"
done
```

### 6. Associative Arrays
Associative arrays use named keys instead of numeric indices (Bash 4+).
  - Declaring an Associative Array:
```bash
declare -A my_dict
my_dict[key1]="value1"
my_dict[key2]="value2"
```
  - Accessing Elements:
```bash
echo "${my_dict[key1]}"  # Outputs 'value1'
```
  - Looping through Associative Arrays:
```bash
for key in "${!my_dict[@]}"; do
  echo "$key: ${my_dict[$key]}"
done
```

### 7. Working with JSON Data
JSON is commonly used for data interchange, and jq is a powerful tool for parsing JSON in Bash scripts.
  - Using jq to Parse JSON:
```bash
jq '.key' file.json
```
  - Example:
```bash
cat data.json | jq '.users[0].name'
```
### 8. Network Requests with curl
The curl command allows you to interact with APIs and download files from the web.
- **Making a GET Request:**
```bash
curl http://example.com
```
- **Making a POST Request with Data:**
```bash
curl -X POST -d "param1=value1&param2=value2" http://example.com
```
- **Working with JSON Data:**
```bash
curl -H "Content-Type: application/json" -d '{"key": "value"}' http://example.com
```
### Practice Exercises

1.  **Regex Search**:
    
    *   Write a script that searches a file for lines that contain email addresses using regex.
        
2.  **Parallel Processing**:
    
    *   Create a script that runs three different commands in parallel and waits for all of them to finish.
        
3.  **JSON Parsing**:
    
    *   Write a script that uses jq to extract a specific value from a JSON file.
        
4.  **Array Manipulation**:
    
    *   Declare an array of file names and loop through the array to check if each file exists.
        
5.  **Network Request**:
    
    *   Use curl to make a GET request to an API and save the response to a file.


---
# 13. Practical Applications of Bash Scripting

Bash scripting is a versatile tool for automating tasks, system administration, data processing, and more. This section explores practical applications of Bash scripting, providing examples you can adapt for everyday tasks and workflows.

---

### 1. Automating System Maintenance

Scripts can automate routine system maintenance tasks such as backups, cleanup, and updates.

- **Automated Backup Script**:
  - This script backs up a specified directory to a backup location.
```bash
  #!/bin/bash
  source_dir="/path/to/source"
  backup_dir="/path/to/backup"
  timestamp=$(date +%Y%m%d_%H%M%S)
  backup_file="$backup_dir/backup_$timestamp.tar.gz"

  tar -czf "$backup_file" "$source_dir"
  echo "Backup completed: $backup_file"
```

- **System Cleanup Script:**
  - This script deletes old log files and frees up disk space.
```bash
#!/bin/bash
find /var/log -name "*.log" -type f -mtime +30 -exec rm {} \;
echo "Old logs cleaned up."
```

### 2. Managing User Accounts
Automate user account creation, deletion, and password resets, especially useful in a multi-user environment.
  - Create New User Accounts:
```bash
#!/bin/bash
for user in user1 user2 user3; do
  sudo adduser "$user"
  echo "$user created successfully."
done
```

- Batch Password Reset:
```bash
#!/bin/bash
for user in $(cat users.txt); do
  echo "$user:NewPassword" | sudo chpasswd
  echo "Password reset for $user"
done
```
### 3. Data Processing and Text Manipulation
Bash scripts can be used to process and analyze data files, especially text-based data formats like CSV or log files.
  - **CSV Data Extraction:**
    - Extract specific columns from a CSV file (e.g., extracting user emails).
```bash
#!/bin/bash
cut -d ',' -f 2 users.csv > emails.txt
echo "Emails extracted to emails.txt"
```
  - **Log Analysis:**
    - This script analyzes a log file for error messages.
```bash
#!/bin/bash
grep -i "error" /var/log/syslog | sort | uniq -c | sort -nr > error_summary.txt
echo "Error summary saved to error_summary.txt"
```

### 4. Automating Network Tasks
Network tasks like ping tests, server monitoring, and file downloads can be automated with Bash.
- Ping Test for Multiple Servers:
```bash
#!/bin/bash
servers=("192.168.1.1" "google.com" "example.com")
for server in "${servers[@]}"; do
  ping -c 1 "$server" &> /dev/null
  if [ $? -eq 0 ]; then
    echo "$server is reachable."
  else
    echo "$server is unreachable."
  fi
done
```
- Automated File Download:
  - This script downloads a list of files from URLs in urls.txt.
```bash
#!/bin/bash
while IFS= read -r url; do
  wget "$url"
done < urls.txt
echo "Files downloaded."
```

### 5. Working with APIs
Bash scripts can interact with web APIs to automate data retrieval and processing.
- **Fetch Weather Information**:
  - This example fetches weather data using curl from a weather API.
```bash
#!/bin/bash
city="London"
api_key="your_api_key_here"
curl "http://api.openweathermap.org/data/2.5/weather?q=$city&appid=$api_key" | jq .
```
- **API Data Processing**:
  - Fetch and process data from a public API.
```bash
#!/bin/bash
curl -s "https://jsonplaceholder.typicode.com/posts" | jq '.[].title' > titles.txt
echo "Post titles saved to titles.txt"
```

### 6. Monitoring and Alerts
Set up simple monitoring and alert scripts to notify you of system or application status changes.
- **Disk Usage Monitoring**:
  - This script checks if disk usage exceeds a specified threshold and sends an alert.
```bash
#!/bin/bash
usage=$(df / | grep / | awk '{print $5}' | sed 's/%//g')
if [ "$usage" -gt 80 ]; then
  echo "Warning: Disk usage is above 80%!" | mail -s "Disk Usage Alert" user@example.com
fi
```
- **Service Status Monitoring**:
  - Check if a service is running and restart it if it’s not.
```bash
#!/bin/bash
service="nginx"
if ! systemctl is-active --quiet "$service"; then
  echo "$service is down. Restarting..."
  systemctl restart "$service"
else
  echo "$service is running."
fi
```

### 7. Task Scheduling with cron
Use cron to schedule your scripts to run at specific times, automating tasks without manual intervention.
- **Setting Up a Cron Job**:
  - Edit crontab with crontab -e and add a job.
  - Example: Run backup every day at midnight.
```bash
0 0 * * * /path/to/backup_script.sh
```
- **Listing Cron Jobs**:
  - Use crontab -l to see all scheduled jobs for the current user

### Practice Exercises

1.  **Automated Backup and Cleanup**:
    
    *   Write a script that backs up files from a specified directory and deletes backups older than 7 days.
        
2.  **User Account Report**:
    
    *   Create a script that generates a report of all user accounts, including their last login time.
        
3.  **Log File Analysis**:
    
    *   Write a script that summarizes the types and counts of errors in a log file.
        
4.  **Server Ping Test**:
    
    *   Write a script that checks if specific servers are reachable and logs the status.
        
5.  **Disk Usage Alert**:
    
    *   Set up a script to monitor disk usage and send an email if it exceeds a certain threshold.

