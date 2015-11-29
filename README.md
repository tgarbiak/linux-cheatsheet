# Linux cheatsheet
Linux cheat sheet. Linux in ?? bullet points. Ubuntu/Debian Edition

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)
http://creativecommons.org/licenses/by-nc-sa/4.0/

## Table of contents
- [Directory structure](#directory-structure)
- [Basic commands](#basic-commands)
- [Files](#files)
- [Users](#users)
- [Programs](#programs)
- [Security](#security)
- [Process management](#process-management)
- [Text processing](#text-processing)
 
## Directory structure

## Basic commands
- `pwd` - prints current/working directory

## Files
- `ls (directory)` lists files in the current or in the specific directory
 - `-l` long list format (more details)
 - `-a` also lists files which name starts from dot ("hidden" files)
 - `-h` file size in human readable format (e.g. `4.0K` instead of `4096`)
- `find` searches for files in the directory tree
 - `find -name 'pattern'` - look for a file which name meets the _pattern_ (e.g. `find -name '*.html'` or `find -name 'id_rsa*'`)
 - `find directory -name 'pattern'` - look for a file with _pattern_ name in the _directory_
- `grep 'pattern' where` - search for a _patter_ within a file, e.g. `grep 'text' ./*.txt` looks for occurrences of "_text_" in all _.txt_ files in the current directory
 - `-P perl-regex` - uses Perl regular expression for _pattern_ (for Perl/PHP lovers)
 - `-E extended-regex` - uses "extended" regular expression for _pattern_
 - `-A number` - in addition to the line where _pattern_ was found also shows _number_ of lines after
 - `-B number` - additionaly shows number of lines before the one where _pattern_ was found

## Users

## Programs
- `which program` tells where the _program_ is located, e.g. `which grep => /bin/grep`

## Security
- port scanning, port blocking, firewall rules, honeypots...

## Process management
- top, kill, etc.

## Text processing
- `tail file` shows the last part of the _file_ (last 10 lines)
 - `-f` outputs the appended data as the file grows ("live update")
 - `-n number` how many lines should be shown
 - can show output from many files at once, e.g. `tail /var/log/*/*.log` or `tail file1 file2`
- less, cat, vim, nano
