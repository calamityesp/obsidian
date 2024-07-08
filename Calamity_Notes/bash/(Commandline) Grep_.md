---
aliases:
  - "(Commandline) Grep "
---

___________________________________________________________________________

Short Description:   Searches for text patterns in files


--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

grep is a command-line utility that searches for text patterns in files. It is commonly used to search for specific strings or patterns of characters in one or more files, or to filter the output of another command.



--------------------------------------------------------------------------------------------------------------------------
                                                    Syntax and more   
--------------------------------------------------------------------------------------------------------------------------
syntax:                         grep PATTERN [OPTION]... [FILE]...


PATTERN is a string or regular expression that grep will search for in the specified FILEs. If no FILE is specified, grep will search for PATTERN in the standard input.

grep has many options that allow you to customize its behavior. Some of the most commonly used options are:

-i or --ignore-case: Ignore case when searching for PATTERN.
-v or --invert-match: Invert the sense of the match, so that grep returns lines that do not match PATTERN.
-n or --line-number: Prefix each line of output with the line number within the input file.
-c or --count: Only print the count of lines that match PATTERN.
-l or --files-with-matches: Only print the names of files that contain a match for PATTERN.
You can learn more about grep and its options by reading the documentation or by searching online for tutorials and examples.


                            --------------------------------------------------------------------
                                                            Options
                            --------------------------------------------------------------------

PATTERN is, by default, a basic regular expression (BRE).

Example: grep -i 'hello world' menu.h main.c

Regexp selection and interpretation:
  -E, --extended-regexp     PATTERN is an extended regular expression (ERE)
  -F, --fixed-strings       PATTERN is a set of newline-separated strings
  -G, --basic-regexp        PATTERN is a basic regular expression (BRE)
  -P, --perl-regexp         PATTERN is a Perl regular expression
  -e, --regexp=PATTERN      use PATTERN for matching
  -f, --file=FILE           obtain PATTERN from FILE
  -i, --ignore-case         ignore case distinctions
  -w, --word-regexp         force PATTERN to match only whole words
  -x, --line-regexp         force PATTERN to match only whole lines
  -z, --null-data           a data line ends in 0 byte, not newline

Miscellaneous:
  -s, --no-messages         suppress error messages
  -v, --invert-match        select non-matching lines
  -V, --version             display version information and exit
  --help                    display this help text and exit

Output control:
  -m, --max-count=NUM       stop after NUM matches
  -b, --byte-offset         print the byte offset with output lines
  --color[=WHEN],
  --colour[=WHEN]           use markers to highlight the matching strings;
                            WHEN is 'always', 'never', or 'auto'
  -o, --only-matching       show only the part of a line matching PATTERN
  -q, --quiet, --silent     suppress all normal output
  -s, --no-messages         suppress error messages
  -U, --binary              treat the file(s) as binary
  -u, --unix-byte-offsets   report offsets as if CRs were not there
  -Z, --null                print 0 byte after FILE name

Context control:
  -A NUM, --after-context=NUM  print NUM lines of trailing context after matching lines
  -B NUM, --before-context=NUM print NUM lines of leading context before matching lines
  -C NUM, --context=NUM        print NUM lines of output context
  -NUM                        same as --context=NUM
  -NUM, --context=NUM          print NUM lines of output context
  --color-context[=WHEN],
  --colour-context[=WHEN]     use markers to highlight context lines;
                              WHEN is 'always', 'never', or 'auto'
  --context=0                 suppress leading context lines
  --label=LABEL               use LABEL as the standard input file name prefix
  -H, --with-filename         print the file name for each match
  -h, --no-filename           suppress the file name prefix on output
  -L, --files-without-match   print only names of FILEs that no match was found
  -l, --files-with-
