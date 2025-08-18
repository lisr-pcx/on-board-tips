# Linux OS

Linux is one of the most versatile operative systems available today. There are different *flavors* but most of the concepts are applicable on any distribution (following notes are based on Debian 11.6).

Makeyou confortable to use linux shell. Most of the time you will connect to a target device using terminal/shell.

## Quick overview on OS

TODO What is an OS.  
TODO Differente layers and components.  

## Basic commands

!!! note
    Some of the commands above shall be run as admin.  
    Add `su` or `sudo` before the desired command to run it with priviledges.

!!! tip
    All the commands have a specific manual page with usage and flags description.
    Check syntax and options to get desired result.    
    `$ man <COMMAND>`

!!! tip
    UNIX derived systems work with the pipeline mechanism, a really cool way to process an output through mutiple stages.  
    Example: if your command return a bigger list of items, you can filter them in order to get only the relevant ones, and then make it scrollable on the screen just by adding:
    `$ <COMMAND> | grep <FILTER> | less`

### Files and folders

```sh
$ pwd

$ ls -la

$ mkdir <DIR PATH>
$ rmdir <DIR PATH>
$ rm -rf <DIR PATH>
$ mv <FILE OR DIR PATH> <NEW FILE OR DIR PATH>
$ cp <FILES OR DIR PATH> <NEW FILES OR DIR PATH>

$ touch <FILE PATH>
$ vi <FILE PATH>
$ nano <FILE PATH>
$ cat <FILE PATH>

$ find <PATH TO LOOK> -name "<FILE>" -print
$ find . -name "*.bak" - print
```

Give folder/file permission:  
Each number has a specific meaning for: user - group - others. Just don't give always full permission to everyone.

+ 0 (binary 000) `---` No permissions at all
+ 1 (binary 001) `--x` Only execute
+ 2 (binary 010) `-w-` Only write
+ 3 (binary 011) `-wx` Write and execute
+ 4 (binary 100) `r--` Only read
+ 5 (binary 101) `r-x` Read and execute
+ 6 (binary 110) `rw-` Read and write
+ 7 (binary 111) `rwx` Read, write, and execute

```sh
$ sudo chmod -R NNN FOLDERPATH 
```

To inspect the raw byte use:

```sh
$ xxd <FILENAME>
$ xxd -ps <FILENAME>
```

### Archives

TAR is a tool to archive files, it creates a single file out of multiple ones (*archiving* .tar file) and if requested it can also reduce the final size (*compression* .tar.gz using GZIP). The final file is often called "tarball".

```sh
$ tar cvf <TARBALL NAME>.tar <SOURCE DIRNAME>
$ tar cvzf <TARBALL NAME>.tar.gz <SOURCE DIRNAME>
$ tar tvf <TARBALL FILE>
$ tar rvf <TARBALL NAME>.tar <FILES OR DIRNAME TO APPEND>
$ tar xvf <TARBALL FILE>
$ tar xvf <TARBALL FILE> -C <DESTINATION DIRNAME>
```

### Install, update, and remove software

Using APT package manager:

```sh
$ apt edit-sources
$ apt update
$ apt list --installed
$ apt show <PACKAGE NAME>
$ apt search <PACKAGE NAME>
$ apt install <PACKAGE NAME>
$ apt remove <PACKAGE NAME>
```

### Processes, applications and devices

```sh
$ top
$ ps -ef
$ ps -ef | grep <APPLICATION NAME>
$ kill <PROCESS ID>
$ sudo dmesg
```

### Editing files

Two editors are always available on Linux systems: `nano` (simple and straightforward) or `vi` (less intuitive but powerful).  
I suggest to learn basic few operations on both editors:

- open, save, save as, close
- search a word
- copy and paste text

```sh
$ vi <FILE PATH>
$ nano <FILE PATH>
```

### Search a pattern

It's useful to find where a pattern or a string has been used on files. The **grep** command is all you need!

```sh
$ grep -Ril "<PATTERN>" <PATH>
$ grep -Ri "<PATTERN>" <PATH>
$ grep -Ri -B5 -A2 "<PATTERN>" <PATH>
```

Filtering for specific files (e.g. cpp, hpp) on desired path:

```sh
$ grep -Ri --include=*.{cpp,hpp} "<PATTERN>" <PATH>
```

### Connect to remote system

Secure SHell is a cryptographic protocol that allows to login into a remote computer.

```sh
$ ssh <USERNAME>@<IPv4 or HOSTNAME>
$ ssh -i <LOCALPATH CERTIFICATE KEY> <USERNAME>@<IPv4 or HOSTNAME>
```