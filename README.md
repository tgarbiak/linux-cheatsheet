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
- `pwd` prints current/working directory
- `sudo <command>` in general: to execute a `<command>` as an other user (e.g. root), usually: executes a command as a super user (e.g. root)

## Files
- `touch <file>` creates a new `<file>` or updates modification time if `<file>` already exists
- `mkdir <directory>` creates a new `<directory>`
- `rm <file>` removes a file
 - `-d` removes a directory (if it's empty)
 - `-r` removes recursively (also removes directories)
 - `-f` ignores problems like nonexistent files, never asks about anything
 - `-i` asks before every removal (paranoid mode)
 - `-I` asks before removing more than 3 files or when removing recursively (safe but not paranoid)
- `ln <target> <link_name>` creates a link of name `<link_name>` to the `<target>`
 - `-s` the link is symbolic (soft), that's usually what you want, especially if you link to a directory
- `cp <source> <destination>` copies `<source>` file to the `<destination>` file
 - `-a source/. destination/` copies all files from the `source` directory to the `destination` directory (preserves folder structure, symbolic links, etc.)
- `mv <source> <destination>` moves `<source>` file to the `<destination>` directory or file, e.g. `mv file1 file2` basically just renames `file1` into `file2`, `mv file1 directory` moves `file1` to the `directory`, `mv file1 directory/file2` moves `file1` into the `directory` and renames the file to `file2`
 - `-f` doesn't ask if some file gets overwritten
- `ls [<directory>]` lists files in the current or in the specific directory
 - `-l` long list format (more details)
 - `-a` also lists files which name starts from dot ("hidden" files)
 - `-h` file size in human readable format (e.g. `4.0K` instead of `4096`)
- `find` searches for files in the directory tree
 - `find -name '<pattern>'` - look for a file which name meets the `<pattern>` (e.g. `find -name '*.html'` or `find -name 'id_rsa*'`)
 - `find <directory> -name '<pattern>'` - look for a file with `<pattern>` name in the `<directory>`
- `grep '<pattern>' [<location>]` - search for a `<pattern>` within a file, optionally in the specific `<location>`, e.g. `grep 'text' ./*.txt` looks for occurrences of "`text`" in all `.txt` files in the current directory
 - `-P <perl-regex>` - uses Perl regular expression for a search pattern (for Perl/PHP lovers)
 - `-E <extended-regex>` - uses "extended" regular expression for a search pattern
 - `-A <number>` - in addition to the line where `<pattern>` was found also shows a _`<number>`_ of lines after
 - `-B <number>` - additionaly shows a `<number>` of lines before the one where `<pattern>` was found 

## Users
- `cat /etc/passwd` to list all users (`cut -d: -f1 /etc/passwd` to just see their names)
- `adduser <username>` adds a new user with name `<username>` (will also ask you to provide a password for that user)
 - `adduser <username> <groupname>` specifies to which group user should be added (or if user already exists adds `<username>` to the `<groupname>`)
 - `--system` to add a system user
- `addgroup <groupname>` adds a new user group
- `deluser <username>` removes a user
 - `--remove-home` removes user's home directory (`/home/<username>`)
 - `--remove-all-files` removes all files owned by the user
 - `--backup` backup files before removing
 - `--system` if user is a system user
- `deluser <username> <groupname>` removes a user from a group (user still exists)
- `delgroup <groupname>` removes a group
 - `--only-if-empty` only remove the group if there are no users in it

## Applications
- `which <application>` tells where the `<application>` is located, e.g. `which grep => /bin/grep`
- `apt-get install <package>` installs `<package>` from the repository
- `apt-get remove <package>` uninstalls `<package>`
 - `apt-get purge <package>` like `remove` but also deletes configuration files, etc.
- `apt-cache search <keyword>` searches apps/packages by `<keyword>`
- `apt-cache show <package>` shows info about app/package (e.g. version and size)
- `apt-add-repository <repository>` adds `<repository>` to the lists of repos (located under `/etc/apt/sources.list` or `/etc/apt/sources.list.d`
 - `-r` removes repo from the list 

## Security
- port scanning, port blocking, firewall rules, honeypots...

## Process management
- top, kill, etc.

## Text processing
- `tail <file>` shows the last part of the `<file>` (last 10 lines)
 - `-f` outputs the appended data as the file grows ("live update")
 - `-n <number>` how many lines should be shown
 - can show output from many files at once, e.g. `tail /var/log/*/*.log` or `tail file1 file2`
- `vim <file>` opens a `<file>` in the vim editor (or `vim` to just open vim)
 - `i` (when inside vim) switches from visual mode to edit mode (other ways: `a`, `I`, `A`)
 - `<Esc>` to switch from either visual or edit mode into a command mode
- Notable `vim` commands:
 - `u` undo (`Ctrl+R` redo)
 - `/<search_pattern>` searches for a `<search_pattern>`
 - `n` go to the next search result
 - `N` go to the previous search result
 - `:e <file>` opens a `<file>`
 - `:q` quits vim
 - `:w` save (write)
 - `:wq` save and quit
 - `:q!` quit without saving
- `cat <file>` shows the content of the `<file>`
 - `-n` with line numbers 
 - can show content of many files at once, e.g. `cat /*.txt` or `cat file1 file2`
- less, nano
