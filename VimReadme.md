i => insert mode (start inserting text at the cursor position)
Esc => return to Normal mode (exit Insert mode or any other mode)
:w => write (save) the current file
:q => quit Vim
:wq => write the file and quit Vim
dd => delete the current line
yy => yank (copy) the current line
p => paste the previously yanked or deleted text
/pattern => search forward for the pattern
?pattern => search backward for the pattern
:%s/pattern/replacement/g => replace all occurrences of pattern with replacement in the entire file
:set syntax=language => set the syntax highlighting to a specific programming language (e.g. :set syntax=python). Vim supports syntax highlighting for: C, C++, Java, Python, Ruby, Perl, JavaScript, HTML, CSS, XML, Markdown, Bash, and many more.
