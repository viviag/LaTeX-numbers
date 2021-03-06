### LaTeX-numbers
Edit numbers formatting in LaTeX files

#### Rules:

There is a dictionary of commands to be excluded from consideration and separate dictionary for commands modifying it's operand to math mode.

All numbers outside of commands must be written in math mode.

Decimals are always written as `d+{,}d+`. All numbers of length more than 4 are splitted by chunks of length three with `\,` space.

Time is interpreted as single number.

Comments are almost never changed.

There must be no excess blank lines and spaces at the ends.

#### Usage:

Works with all .tex files in a directory.


Typical case:
`LaTeX-numbers -d <path to dictionary> -m <path to dictionary of math mode> <path to directory to work in>`.

For complete reference call `LaTeX-numbers -h`. **Important notice:** By default tool works in place of files. Enable writing to copies with `.test` extension by `-D` option.

Output of embedded help message:
```
Fix number formatting through directory.

Usage: LaTeX-numbers (-d|--dict DICT) [-m|--math MATH] PATH [-D|--debug]
                     [-R|--regex]

Available options:
  -h,--help                Show this help text
  -d,--dict DICT           File with list of expressions not to change numbers
                           in.
  -m,--math MATH           Nontrivial commands enabling math mode as side effect
                           for text inside.
  PATH                     Directory with LaTeX to fix.
  -D,--debug               Write changes to another file (debug mode).
  -R,--regex               Read dictionary entries as plain regular expressions.
```

Dictionaries contain templates for LaTeX commands with arguments. They support line comments in Haskell syntax. Special sequences are `##` and `#$`, which are equivalent to `(?s).*?` and `.*?` correspondingly.
`dict.txt` and `math_dict.txt` files are given here for example and are battle tested. They're annotated in Russian, I can annotate them in English on a request.

**Disclaimer**

This script is not an excuse to forget habitual techniques of page making. It should be used at the end of the process to ensure everything is ok. And it is an excuse not to make edits if they're in numbers only.
