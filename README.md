 PyComGrader: A Python Module for Grading C++ Programs
=====================================================

Introduction
------------

PyComGrader is a Python module designed to help educators and students easily evaluate and grade C++ programs against multiple test cases. It provides a simple and efficient way to test programs against multiple test cases and can be used on multiple platforms, including Windows and Linux. The module can be used as a command-line tool and provides various options to customize the grading process. PyComGrader aims to simplify the process of setting up training contests offline, testing problems against multiple test cases during a contest to get preliminary results, and helping prepare and form competitive programmers. However, please note that this module is not intended for official contests and is solely meant as an educational tool.

Features
--------

The following features are included in PyComGrader:

* Initialize a `Grader` class with a file to test, a time limit, and a memory limit.
* Automatic comparison of outputs: PyComGrader automatically compares the program's output to the expected output.
* Methods to test the given input against sets of test cases or individual tests.
* Support for both a command-line interface and Python API.
* Customizable test case directories and filenames.
* Optional support for g++ C++ compiler (recommended).
* Easy installation using `pip install pycomgrader`.

Getting Started
---------------

To start using PyComGrader, follow these steps:

1. Install PyComGrader by running `pip install pycomgrader` in your terminal.
2. Import the necessary modules: `from pycomgrader import Grader`.
3. Create a `Grader` object with the file to test, time limit, and memory limit: `grader = Grader(2000, 128, exec_file = 'my_program')`
4. Create a corresponding directory for the test cases, and place the input files (with the extension `.in`) and expected output files (with the extension `.out`) inside. The filenames for the input and output files can be arbitrary, but they must have the same name. For example, you can have 01.in, 01.out, 02.in, 02.out, etc.
5. Test the program against one or more test cases using the `grader.grade('test_cases_dir')` method.

Command Line Interface
----------------------

PyComGrader can be used as a command-line tool by running `pycomgrader` followed by the path to the file to test and the directory with the test cases. For example:
```bash
$ pycomgrader my_program.cpp test_cases_dir
```
You can specify the time limit (milliseconds) and memory limit (megabytes) as positional arguments respectively:
```bash
$ pycomgrader my_program.cpp test_cases_dir 1000 32
```
One of the key features of PyComGrader is its ability to execute C++ programs directly, without the need for a separate compiler. This makes it easy to use on systems where a C++ compiler is not installed, or where the user has other means of compiling their source code. Users can use the `-e` flag when running PyComGrader to indicate that a file should be executed directly.
```bash
$ pycomgrader my_program test_cases_dir -e
```
This will tell PyComGrader to execute the contents of `my_program` directly, rather than compiling it first.

Requirements
------------

PyComGrader requires the following packages to be installed:

* Psutil
* Rich
* PathType

Optional Dependencies
-----------------------

While not required, we recommend installing g++ C++ compiler to compile and run the tested programs.

Tips and Tricks
--------------

Here are some tips and tricks to help you get the most out of PyComGrader:

* Use descriptive names for your test cases, so you can easily identify what each test case is checking.
* Write comprehensive test cases to cover all aspects of the student's code.
* For detailed usage information, run `pycomgrader --help`:
  ```
  offline grader for C++ programs

  positional arguments:
    file              path to the program to submit
    dir               path to the directory containing the test cases
    time              maximum amount of time (in milliseconds) to run the program
    mem               maximum amount of memory (in megabytes) to allocate to the program

  options:
    -h, --help        show this help message and exit
    -e, --executable  notifies the grader that the file is executable
  ```

Troubleshooting
---------------

If you encounter any issues while using PyComGrader, refer to the troubleshooting guide below:

* Q: My test cases are not being recognized. What do I do?

  A: Check that your test cases are named correctly (i.e., with the extension `.in` for inputs and `.out` for expected outputs).

* Q: PyComGrader is taking too long to run. What do I do?

  A: Try reducing the number of test cases you are running at once.

* Q: Does PyComGrader support other programming languages besides C++  
  
  A: While PyComGrader was originally designed for grading C++ programming assignments because it is a widely used language in the competitive programming community, it can be extended to support other programming languages. By modifying the code to recognize and run programs for the language you want to support, you can use PyComGrader to grade assignments written in other languages. The use of a virtual environment is recommended if this is the case.

* Q: PyComGrader is giving me a compile error. What do I do?
  
  A: Check if g++ is installed and accessible as a system command. You can do this by opening a terminal and running `g++ --version`. If g++ is not installed, you can install it using your operating system's package manager. If g++ is installed but not accessible, you may need to modify your system's PATH environment variable to include the directory where g++ is installed.

License
-------

PyComGrader is released under the MIT License. See LICENSE for details.
