---
title: JumboShell
date: February 2024
course: CS111 - Operating Systems
github_repo: https://github.com/rusny23/shell_emulator
link_name: JumboShell
layout: project
---

This project implements a custom shell called `jumboshell`. This shell allows users to execute commands with or without arguments 
similar to traditional shells like Bash. It supports piping ('|'), which allows users to chain commands by passing the output of one
command as the input to the next.

### Features:

- **Command Execution**: Execute standard Unix commands (e.g., `ls`, `grep`).
- **Piping**: Support for piping between multiple commands.
- **Custom Prompt**: A simple shell prompt (`jsh$`) to indicate to the user that it is ready for input.
- **Graceful Exit**: Type `exit` to close the shell.

### Requirements:
- GCC Compiler

### Usage

- **Compile**: Use command `gcc` to compile the source code:
   ```bash
   gcc -o jumboshell shell.c
   ```

### Examples:

Lets say we had a file called p3.c which looked like this:

``` c
int main(int argc, char *argv[]){ 
    printf("Hello");
    return 0;
}
```

Simple Unix-like command without any arguments or piping:

``` bash
> jsh$ ls
Makefile	p3.c		shell.c		vgcore.994286
jumboshell	shell		shell.o
jsh status: 0
```
Command with multiple arguments:

``` bash
> jsh$ wc -l -w -c p3.c
       3       9      71 p3.c
jsh status: 0
jsh$ find . -type f -name "*.c"
./shell.c
./p3.c
jsh status: 0
```

Command with piping:

``` bash
> jsh$ cat p3.c | sort | uniq -c | sort -nr
   1 }
   1 int main(int argc, char *argv[]){ 
   1 //test file used as input for the shell
   1     return 0;
   1     printf("Hello");
   1 
jsh status: 0
```
Error command:

```bash
> jsh$ hfgfh
execvp: No such file or directory
jsh status: 127
```

**Notes:**

All lines from the shell start with "jsh" followed by the "$" symbol as the prompt.
The shell handles pipelines by concurrently executing commands in the pipeline.
Error messages are displayed for command not found and file not found errors.
Proper handling of child processes to prevent zombie processes.