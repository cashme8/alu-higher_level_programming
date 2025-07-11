# python-inheritance

## Description
This project introduces key concepts of Python inheritance, class hierarchies, and object-oriented programming.
We work with base classes, subclasses, and practice validating data and overriding methods like __str__() and area().

### Key Concepts
Python class inheritance

super() function usage

Private attributes

Method overriding

Data validation within classes

Custom __str__() methods

## Files and Functionalities
Filename    Description
0-lookup.py Function that returns a list of available attributes and methods of an object
1-my_list.py    Class MyList inheriting from list with a method print_sorted()
2-is_same_class.py  Function that checks if an object is exactly an instance of a specified class
3-is_kind_of_class.py   Function that checks if an object is an instance of a class or its subclass
4-inherits_from.py  Function that checks if an object inherits from a class
5-base_geometry.py  Empty class BaseGeometry
6-base_geometry.py  Class BaseGeometry with area() method raising NotImplementedError
7-base_geometry.py  Adds integer_validator method to BaseGeometry
8-rectangle.py  Class Rectangle inheriting from BaseGeometry, validating width & height
9-rectangle.py  Adds area() and __str__() to Rectangle class
10-square.py    Class Square inheriting from Rectangle with size validation
11-square.py    Adds custom __str__() to Square class

## Requirements
Python 3.8.5

Ubuntu 20.04 LTS

No external Python packages allowed

Code must pass pycodestyle (PEP8) checks

Files must have executable permissions

Usage Example
### Clone the repository:

bash

git clone https://github.com/yourusername/alu-higher_level_programming.git
cd python-inheritance
Run main files for each task to test functionalities:

bash

./0-main.py
./1-main.py
...
## Author
Created as part of ALU Higher Level Programming module.
By: KABANDA GISLAIN
