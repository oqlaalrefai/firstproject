## regular expression (regex)
- are a sequence of characters used to check whether a pattern exists in a given text (string) or not
- They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.
#### Regular Expressions in Python
- to use regex you should import this package `import re`

- Ordinary Characters:
  - do not have a special meaning in their regular expression syntax.
  - `re.match(pattern,sequence)` to check if the pattern match the sequence
  - `pattern = r"Cookie" `
    - `r` This is called a raw string literal. It changes how the string literal is interpreted. Such literals are stored as they appear.
- Wild Card Characters: Special Characters
  -  have a special meaning when used in a regular expression.
  - `search()` you scan through the given string/sequence, looking for the first location where the regular expression produces a match.
  - `group()` returns the string matched by the re
  - `$` Matches the end of string.
  - `[abc]` Matches a or b or c.
  - `[a-zA-Z0-9]` Matches any letter from (a to z) or (A to Z) or (0 to 9)
  - character of the set is `^` all the characters that are not in the set will be matched.
  - `\` Backslash.:
    - If the character following the backslash is a recognized escape character
    - character following the `\` is not a recognized escape character, then the `\`is treated like any other character and passed through
    - `\` can be used in front of all the metacharacters to remove their special meaning
    - `\w` Lowercase 'w'. Matches any single letter, digit, or underscore.
    - `\W` Uppercase 'W'. Matches any character not part of `\w`
    - `\s` Lowercase 's'. Matches a single whitespace character like: space, newline, tab, return. 
    - `\S` Uppercase 'S'. Matches any character not part of `\s`
    - `\d` Lowercase d. Matches decimal digit 0-9.
    - `\D` Uppercase d. Matches any character that is not a decimal digit.
    - `+` symbol used after the \d in the example above is used for repetition
    - `\t` Lowercase t. Matches tab.
    - `\n` Lowercase n. Matches newline.
    - `\r` Lowercase r. Matches return.
    - `\A` Uppercase a. Matches only at the start of the string. Works across multiple lines as well.
    - `\Z` Uppercase z. Matches only at the end of the string.
    - `^` and `\A` are effectively the same, and so are `$` and `\Z`. Except when dealing with MULTILINE mode
    - `\b` Lowercase b. Matches only the beginning or end of the word.
    - `{ }` Checks for an explicit number of times.
    - `.` A period. Matches any single character except the newline character

- Repetitions:
  - `+` Checks if the preceding character appears one or more times starting from that position.
  - `*` Checks if the preceding character appears zero or more times starting from that position
  - `?` Checks if the preceding character appears exactly zero or one time starting from that position.
  - `{x}` Repeat exactly x number of times.
  - `{x,}` Repeat at least x times or more.
  - `{x, y}` Repeat at least x times but no more than y times
  - The `+` and `*` qualifiers are said to be greedy

- Grouping in Regular Expressions:
The group feature of regular expression allows you to pick up parts of the matching text. Parts of a regular expression pattern bounded by parenthesis `()` are called groups
  - `<>` brackets This will let you create named groups.
  - The syntax for creating named group is: `(?P<name>...)`. Replace the `name` part with the name you want to give to your group.

- Greedy vs. Non-Greedy Matching:
When a special character matches as much of the search sequence (string) as possible, it is said to be a "Greedy Match".
  - The pattern `<.*>` matched the whole string, right up to the second occurrence of `>`.
  - `*?` that matches as little text as possible.

#### Function provided by 're'
1. `search(pattern, string, flags=0)` :
  - With this function, you scan through the given string/sequence, looking for the first location where the regular expression produces a match
2. `match(pattern, string, flags=0)`
  - Returns a corresponding match object if zero or more characters at the beginning of string match the pattern. Else it returns None
3. `findall(pattern, string, flags=0)`
  - Finds all the possible matches in the entire sequence and returns them as a list of strings. Each returned string represents one match.
4. `finditer(string, [position, end_position])`
  - it finds all the possible matches in the entire sequence but returns regex match objects as an iterator.
  - excellent choice when you want to have more information returned to you about your search. The returned regex match object holds not only the sequence that matched but also their positions in the original text.
5. `sub(pattern, repl, string, count=0, flags=0)`
  - is the substitute function. It returns the string obtained by replacing or substituting the leftmost non-overlapping occurrences of pattern in string by the replacement repl. If the pattern is not found, then the string is returned unchanged.
6. `subn(pattern, repl, string, count=0)`
  - it returns a tuple containing the new string value and the number of replacements that were performed in the statement.
7. `split(string, [maxsplit = 0])`
  - This splits the strings wherever the pattern matches and returns a list. If the optional argument maxsplit is nonzero, then the maximum 'maxsplit' number of splits are performed.
8. `start()`
  - Returns the starting index of the match.
9. `end()`
  - Returns the index where the match ends.
10. `span()`
  - Return a tuple containing the (start, end) positions of the match
#### You can add flags as an extra argument to the different functions that you have seen in this tutorial. Some of the more useful ones are:

1. `IGNORECASE (I)` Allows case-insensitive matches.
2. `DOTALL (S)` Allows . to match any character, including newline.
3. `MULTILINE (M)` Allows start of string (^) and end of string ($) anchor to match newlines as well.
4. `VERBOSE (X)` Allows you to write whitespace and comments within a regular expression to make it more readable. 


# shutil 
— High-level File Operations
- `copyfile()` copies the contents of the source to the destination and raises IOError if it does not have permission to write to the destination file.
- By default when a new file is created under Unix, it receives permissions based on the umask of the current user. To copy the permissions from one file to another, use `copymode()`
- To copy other metadata about the file use `copystat()`.
  - Only the permissions and dates associated with the file are duplicated with `copystat()`.

### Working With Directory Trees
- To copy a directory from one place to another, use `copytree()`accepts two callable arguments to control its behavior:
  - The ignore argument is called with the name of each directory or subdirectory being copied along with a list of the contents of the directory. It should return a list of items that should be copied. 
  - The copy_function argument is called to actually copy the file.
- The symlinks argument controls whether symbolic links are copied as links or as files. The default is to copy the contents to new files. If the option is true, new symlinks are created within the destination tree.
- `ignore_patterns()` is used to create an ignore function to skip copying Python source files
- `verbose_copy()` prints the names of files as they are copied
- `rmtree()` To remove a directory and its contents.
- `move()` To move a file or directory from one place to another.
- `which()` scans a search path looking for a named file

### Archives
Python’s standard library includes many modules for managing archive files such as tarfile and zipfile. There are also several higher-level functions for creating and extracting archives in shutil. get_archive_formats() returns a sequence of names and descriptions for formats supported on the current system.

- `make_archive()` to create a new archive file.
  - `root_dir` argument to move to a new relative position on the filesystem 
  - `base_dir` argument to specify a directory to add to the archive.

- shutil maintains a registry of formats that can be unpacked on the current system, accessible via `get_unpack_formats()`.
- Extract the archive with `unpack_archive()`

### File System Space
It can be useful to examine the local file system to see how much space is available before performing a long running operation that may exhaust that space
- `disk_usage()` returns a tuple with the total space, the amount currently being used, and the amount remaining free.

