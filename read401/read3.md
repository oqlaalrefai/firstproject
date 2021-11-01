# Read & Write Files in Python
Files on most modern file systems are composed of three main parts:
  - Header,Data,End of file (EOF)
## path
The file path is a string that represents the location of a file. It’s broken up into three major parts:
- Folder Path
- File Name
- Extension
- You can use the special characters double-dot (..) to move one directory up
 An encoding is a translation from byte data to human readable characters.
 The two most common encodings are the ASCII and UNICODE Formats

## Opening and Closing a File in Python
to `open()` has a single required argument that is the path to the file 
to close file use `close()`
Other options for modes the most commonly used ones:
  - 'r'	Open for reading (default)
  - 'w'	Open for writing, truncating (overwriting) the file first
  - 'rb' or 'wb'	Open in binary mode (read/write using byte data)
- There are three different categories of file objects:
  - Text files
  - Buffered binary files
  - Raw binary files

|Method	|What It Does|
| ----------------- | --------------------------------------------------------------------------------------- |
|.read(size=-1)	|This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.|
|.readline(size=-1)	|This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.|
|.readlines()|	This reads the remaining lines from the file object and returns them as a list.|

## Iterating Over Each Line in the File
A common thing to do while reading a file is to iterate over each line. Here’s an example of how to use the Python .readline()

##  writing files
|Method	What| It Does|
|-----------| -------|
|.write(string)|	This writes the string to the file.|
|.writelines(seq)|	This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).|
## Working With Bytes
This is done by adding the 'b' character to the mode argument `with open('dog_breeds.txt', 'rb')`

## Tips and Tricks
The `__file__`attribute is a special attribute of modules, similar to `__name__`. It is:

“the pathname of the file from which the module was loaded, if it was loaded from a file.”

## Appending to a File
```
with open('dog_breeds.txt', 'a') as a_writer:
    a_writer.write('\nBeagle')
```

## built-in libraries out there that you can use to help you:

  - wave: read and write WAV files (audio)
  - aifc: read and write AIFF and AIFC files (audio)
  - sunau: read and write Sun AU files
  - tarfile: read and write tar archive files
  - zipfile: work with ZIP archives
  - configparser: easily create and parse configuration files
  - xml.etree.ElementTree: create or read XML based files
  - msilib: read and write Microsoft Installer files
  - plistlib: generate and parse Mac OS X .plist files

## there are even more third party tools available on PyPI. Some popular ones are the following:
  - PyPDF2: PDF toolkit
  - xlwings: read and write Excel files
  - Pillow: image reading and manipulation

# Exceptions
## Exceptions versus Syntax Errors
- Syntax errors occur when the parser detects an incorrect statement
- exception error. This type of error occurs whenever syntactically correct Python code results in an error
## Raising an Exception
- We can use raise to throw an exception if a condition occurs. 
```
x = 10
if x > 5:
raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```
## The AssertionError Exception
Instead of waiting for a program to crash midway, you can also start by making an assertion in Python
```
import sys
assert ('linux' in sys.platform), "This code runs on Linux only."
```
## The try and except Block: Handling Exceptions
The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.
## The else Clause
In Python, using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.

## Cleaning Up After Using finally
Imagine that you always had to implement some sort of action to clean up after executing your code. Python enables you to do so using the finally clause.