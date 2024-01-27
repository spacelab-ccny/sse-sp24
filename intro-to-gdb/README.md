# Introduction to `gdb`

`gdb` is a debugger for C (and C++) and other languages. It allows you to do things like run the program up to a certain point then stop and print out the values of certain variables at that point, or step through the program one line at a time and print out the values of each variable after executing each line. It uses a command line interface.

This exercise will help you get the basics of `gdb`, which you will use extensively on Assignment 1. As you learn `gdb`, you can use [reference cards](https://gabriellesc.github.io/teaching/resources/GDB-cheat-sheet.pdf) to help you remember the correct command invocations.

To prepare your program for debugging with `gdb`, you must compile it with the `-g` flag. So, if your program is in a source file called `example.c` and you want to put the executable in the file `example`, then you would compile with the following command:

```console
$ gcc -g -o example example.c
```

To start `gdb` on a program `example`, just type in:

```console
$ gdb example
```

`gdb` will give you a prompt that looks like this: 

```console
(gdb)
```

From that prompt you can run your program, look at variables, etc., using [various commands](https://gabriellesc.github.io/teaching/resources/GDB-cheat-sheet.pdf). Quit `gdb` by typing in `q`.

## Activity 

For today's exercise, we will use the following commands:

```console
$ gcc -g -std=c99 -w fixed.c -o fixed -lm
$ gcc -g -std=c99 -w buggy.c -o buggy -lm
```

- `-w`: suppresses the warnings
- `-std=c99`:  the `std` flag sets the C standard version, which we set to C99 (allowing for in-line for loops)
- `-lm`: to link to the math library when building the executable

There are three bugs in the code `buggy.c`. The program is meant to find the sum of the first 10 prime numbers. A prime number is a number that is only divisible by itself and 1 (excluding the number 1). For example: 2, 3, 5, 7, 11, etc. The program should output the result 129.

We will work on the first bug together using `gdb`. Try to fix the other two bugs in the program using `gdb` on your own time. This will not be graded, but mastering `gdb` will be very useful as you work on Assignment 1.
