---
aliases:
  - "(Commandline) Diff  tool "
tags:
  - Keep/Label/commandline
  - Keep/Label/Shell-Commands
---

___________________________________________________________________________

Short Description:   tool used to find the difference between multiple files


--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

The diff command is a Unix utility that allows you to compare the contents of two files, or the output of two commands. Here are some options you can use with diff:



-------------------------------------------------------------------------------------------------------------------------                                                                    
                                                   Common Options
--------------------------------------------------------------------------------------------------------------------------
-u or --unified: 
     Output the difference between the two files in a unified context format. This shows three lines of context, with the line being removed or added indicated by a leading - or + symbol.

-w or --ignore-all-space: 
     Ignore white space when comparing files.

-i or --ignore-case: 
     Ignore case when comparing files.

-q or --brief: 
     Output only whether the files are different or not, rather than the full diff.

-N or --new-file: 
     Treat absent files as empty.

-r or --recursive: 
     Recursively compare subdirectories.


                            --------------------------------------------------------------------
                                                         example
                            --------------------------------------------------------------------

Comparing two versions of a file to see what changes have been made:
diff file1.txt file2.txt

Comparing the output of two commands:
diff <(command1) <(command2)

Recursively comparing the contents of two directories:
diff -r dir1 dir2

Basic file comparing:
diff -u original_file modified_file > patch_file.patch


                            --------------------------------------------------------------------
                                                         All Options
                            --------------------------------------------------------------------

Usage: diff [OPTION]... FILES
Compare FILES line by line.

Mandatory arguments to long options are mandatory for short options too.
  -i  --ignore-case       ignore case differences
  -E  --ignore-tab-expansion  ignore changes due to tab expansion
  -b  --ignore-space-change  ignore changes in the amount of white space
  -w  --ignore-all-space  ignore all white space
  -B  --ignore-blank-lines  ignore changes whose lines are all blank
  -I RE  --ignore-matching-lines=RE  ignore changes whose lines all match RE
  -a  --text              treat all files as text
  -u  --unified[=LINES]   output NUM (default 3) lines of unified context
  -U  --unidirectional-new-file  treat absent file as empty
  -p  --show-c-function   show which C function each change is in
  -F  --show-function-line=RE  show the most recent line matching RE
  -q  --brief             report only when files differ
  -N  --new-file          treat absent files as empty
  -T  --initial-tab       make tabs line up by prefixing a tab
  -Z  --zero-terminated   end lines with 0 byte, not newline
  -r  --recursive         recursively compare any subdirectories found
  -P  --unified-per-function  like -u, but reports changes only in function
  --label LABEL           use LABEL instead of file name
  -L  --label LABEL       use LABEL instead of file name
  -t  --expand-tabs       expand tabs to spaces in output
  -T  --initial-tab       make tabs line up by prefixing a tab
  -W  --width=WIDTH       output at most WIDTH (default 130) print columns
  -y  --side-by-side      output in two columns
  -c  --context[=LINES]   output NUM (default 3) lines of copied context
  -D  --ifdef=NAME        output merged file with `#ifdef NAME' diffs
  -S FILE  --starting-file=FILE  start with FILE when comparing directories
  -H  --speed-large-files  assume large files and many scattered small changes
  --horizon-lines=LINES   keep LINES lines of the common prefix and suffix
  --help                  display this help and exit
  --version               output version information and exit

The following options are useful for ignoring changes that are not relevant
when preparing context for translations, but they are all more expensive.
  -x REGEX  --exclude=REGEX  skip files that match REGEX
  -X FILE   --exclude-from=FILE   skip files that match any pattern in FILE
  -d  --minimal            try hard to find a smaller set of changes
  -D  --ifdef=NAME         output merged file with `#ifdef NAME' diffs
  --color                  use colors to highlight changes
  --color-words            colorize changed words, not just the whole line
  -G  --color-granularity=WORD  color words that