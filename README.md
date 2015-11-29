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
- [Applications](#applications)
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
 - `find -name 'pattern'` - look for a file which name meets the _`pattern`_ (e.g. `find -name '*.html'` or `find -name 'id_rsa*'`)
 - `find directory -name 'pattern'` - look for a file with _`pattern`_ name in the _`directory`_
- `grep 'pattern' where` - search for a _`pattern`_ within a file, e.g. `grep 'text' ./*.txt` looks for occurrences of "_`text`_" in all _`.txt`_ files in the current directory
 - `-P perl-regex` - uses Perl regular expression for a _`pattern`_ (for Perl/PHP lovers)
 - `-E extended-regex` - uses "extended" regular expression for a _`pattern`_
 - `-A number` - in addition to the line where _`pattern`_ was found also shows a _`number`_ of lines after
 - `-B number` - additionaly shows a _`number`_ of lines before the one where _`pattern`_ was found

## Users

## Applications
- `which application` tells where the _`application`_ is located, e.g. `which grep => /bin/grep`

## Security
- port scanning, port blocking, firewall rules, honeypots...

## Process management
- top, kill, etc.

## Text processing
- `tail file` shows the last part of the _`file`_ (last 10 lines)
 - `-f` outputs the appended data as the file grows ("live update")
 - `-n number` how many lines should be shown
 - can show output from many files at once, e.g. `tail /var/log/*/*.log` or `tail file1 file2`
- `vim file` opens a file in the vim editor (or `vim` to just open the vim editor)
 - `i` to switch from visual mode to edit mode (other ways: `a`, `I`, `A`)
 - `<Esc>` to switch from either visual or edit mode into command mode
 - Notable commands:
  - `u` undo (`Ctrl+R` redo)
  - `/search_pattern` searches for a _`search_pattern`_
  - `n` search next
  - `N` search prev
  - `:e file` opens a _`file`_
  - `:q` quits vim
  - `:w` save (write)
  - `:qw` save and quit
  - `:q!` quit without saving
- `cat file` shows the content of the _`file`_
 - `-n` with line numbers 
 - can show content of many files at once, e.g. `cat /*.txt` or `cat file1 file2`
- less, nano
