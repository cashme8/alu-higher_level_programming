#  python-exceptions Project


This project is part of the ALU Higher Level Programming track. It focuses on handling **exceptions** in Python — a critical skill for writing safe, crash-proof code.

##  Project Directory: `python-exceptions`

### What Each File Does

- **1-safe_print_integer.py**  
  Safely prints an integer using `"{:d}".format()`. Returns `True` if successful, otherwise `False`.

- **2-safe_print_list_integers.py**  
  Prints the first `x` elements of a list, but only integers. Skips non-integers silently and counts how many were printed.

- **3-safe_print_division.py**  
  Divides two integers and prints the result in the `finally` block. Handles division by zero.

- **4-list_division.py**  
  Divides two lists element by element. Handles all errors with clear messages like `wrong type`, `division by 0`, or `out of range`.

- **5-raise_exception.py**  
  Raises a `TypeError` intentionally — useful for learning how custom exceptions work.

- **6-raise_exception_msg.py**  
  Raises a `NameError` with a custom message passed as an argument.

---

## Skills Practiced

- `try` / `except` / `finally`
- Custom exception raising
- Input validation
- Safe formatting and printing


## No external libraries used

This project uses **pure Python**, as per the exercise rules.

Done by **KABANDA GISLAIN**

## These are the questions
1. Safe printing of an integers list
mandatory
Write a function that prints an integer with "{:d}".format().

Prototype: def safe_print_integer(value):
value can be any type (integer, string, etc.)
The integer should be printed followed by a new line
Returns True if value has been correctly printed (it means the value is an integer)
Otherwise, returns False
You have to use try: / except:
You have to use "{:d}".format() to print as integer
You are not allowed to import any module
You are not allowed to use type()
guillaume@ubuntu:~/$ cat 1-main.py
#!/usr/bin/python3
safe_print_integer = __import__('1-safe_print_integer').safe_print_integer

value = 89
has_been_print = safe_print_integer(value)
if not has_been_print:
    print("{} is not an integer".format(value))

value = -89
has_been_print = safe_print_integer(value)
if not has_been_print:
    print("{} is not an integer".format(value))

value = "School"
has_been_print = safe_print_integer(value)
if not has_been_print:
    print("{} is not an integer".format(value))

guillaume@ubuntu:~/$ ./1-main.py
89
-89
School is not an integer
guillaume@ubuntu:~/$ 
Repo:

GitHub repository: alu-higher_level_programming
Directory: python-exceptions
File: 1-safe_print_integer.py
 
0/14 pts
2. Print and count integers
mandatory
Write a function that prints the first x elements of a list and only integers.

Prototype: def safe_print_list_integers(my_list=[], x=0):
my_list can contain any type (integer, string, etc.)
All integers have to be printed on the same line followed by a new line - other type of value in the list must be skipped (in silence).
x represents the number of elements to access in my_list
x can be bigger than the length of my_list - if it’s the case, an exception is expected to occur
Returns the real number of integers printed
You have to use try: / except:
You have to use "{:d}".format() to print an integer
You are not allowed to import any module
You are not allowed to use len()
guillaume@ubuntu:~/$ cat 2-main.py
#!/usr/bin/python3
safe_print_list_integers = \
    __import__('2-safe_print_list_integers').safe_print_list_integers

my_list = [1, 2, 3, 4, 5]

nb_print = safe_print_list_integers(my_list, 2)
print("nb_print: {:d}".format(nb_print))

my_list = [1, 2, 3, "School", 4, 5, [1, 2, 3]]
nb_print = safe_print_list_integers(my_list, len(my_list))
print("nb_print: {:d}".format(nb_print))

nb_print = safe_print_list_integers(my_list, len(my_list) + 2)
print("nb_print: {:d}".format(nb_print))

guillaume@ubuntu:~/$ ./2-main.py
12
nb_print: 2
12345
nb_print: 5
12345Traceback (most recent call last):
  File "./2-main.py", line 14, in <module>
    nb_print = safe_print_list_integers(my_list, len(my_list) + 2)
  File "//2-safe_print_list_integers.py", line 7, in safe_print_list_integers
    print("{:d}".format(my_list[i]), end="")
IndexError: list index out of range
guillaume@ubuntu:~/$ 
Repo:

GitHub repository: alu-higher_level_programming
Directory: python-exceptions
File: 2-safe_print_list_integers.py
 
0/13 pts
3. Integers division with debug
mandatory
Write a function that divides 2 integers and prints the result.

Prototype: def safe_print_division(a, b):
You can assume that a and b are integers
The result of the division should print on the finally: section preceded by Inside result:
Returns the value of the division, otherwise: None
You have to use try: / except: / finally:
You have to use "{}".format() to print the result
You are not allowed to import any module
guillaume@ubuntu:~/$ cat 3-main.py
#!/usr/bin/python3
safe_print_division = __import__('3-safe_print_division').safe_print_division

a = 12
b = 2
result = safe_print_division(a, b)
print("{:d} / {:d} = {}".format(a, b, result))

a = 12
b = 0
result = safe_print_division(a, b)
print("{:d} / {:d} = {}".format(a, b, result))

guillaume@ubuntu:~/$ ./3-main.py
Inside result: 6.0
12 / 2 = 6.0
Inside result: None
12 / 0 = None
guillaume@ubuntu:~/$ 
Repo:

GitHub repository: alu-higher_level_programming
Directory: python-exceptions
File: 3-safe_print_division.py
 
0/10 pts
4. Divide a list
mandatory
Write a function that divides element by element 2 lists.

Prototype: def list_division(my_list_1, my_list_2, list_length):
my_list_1 and my_list_2 can contain any type (integer, string, etc.)
list_length can be bigger than the length of both lists
Returns a new list (length = list_length) with all divisions
If 2 elements can’t be divided, the division result should be equal to 0
If an element is not an integer or float:
print: wrong type
If the division can’t be done (/0):
print: division by 0
If my_list_1 or my_list_2 is too short
print: out of range
You have to use try: / except: / finally:
You are not allowed to import any module
guillaume@ubuntu:~/$ cat 4-main.py
#!/usr/bin/python3
list_division = __import__('4-list_division').list_division

my_l_1 = [10, 8, 4]
my_l_2 = [2, 4, 4]
result = list_division(my_l_1, my_l_2, max(len(my_l_1), len(my_l_2)))
print(result)

print("--")

my_l_1 = [10, 8, 4, 4]
my_l_2 = [2, 0, "H", 2, 7]
result = list_division(my_l_1, my_l_2, max(len(my_l_1), len(my_l_2)))
print(result)

guillaume@ubuntu:~/$ ./4-main.py
[5.0, 2.0, 1.0]
--
division by 0
wrong type
out of range
[5.0, 0, 0, 2.0, 0]
guillaume@ubuntu:~/$ 
Repo:

GitHub repository: alu-higher_level_programming
Directory: python-exceptions
File: 4-list_division.py
 
0/16 pts
5. Raise exception
mandatory
Write a function that raises a type exception.

Prototype: def raise_exception():
You are not allowed to import any module
guillaume@ubuntu:~/$ cat 5-main.py
#!/usr/bin/python3
raise_exception = __import__('5-raise_exception').raise_exception

try:
    raise_exception()
except TypeError as te:
    print("Exception raised")

guillaume@ubuntu:~/$ ./5-main.py
Exception raised
guillaume@ubuntu:~/$ 
Repo:

GitHub repository: alu-higher_level_programming
Directory: python-exceptions
File: 5-raise_exception.py
 
0/11 pts
6. Raise a message
mandatory
Write a function that raises a name exception with a message.

Prototype: def raise_exception_msg(message=""):
You are not allowed to import any module
guillaume@ubuntu:~/$ cat 6-main.py
#!/usr/bin/python3
raise_exception_msg = __import__('6-raise_exception_msg').raise_exception_msg

try:
    raise_exception_msg("C is fun")
except NameError as ne:
    print(ne)

guillaume@ubuntu:~/$ ./6-main.py
C is fun
guillaume@ubuntu:~/$ 
Repo:

GitHub repository: alu-higher_level_programming
Directory: python-exceptions
File: 6-raise_exception_msg.py
 

