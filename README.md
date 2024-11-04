

# `lines`

A small bash utility for selecting an line and optionally running a command.


## Usage:

The `lines` command has two modes of operation. Without arguments, it enumerates the lines read from stdin. With a numerical argument it "selects" that line and filters the rest. With an optional second argument `command` it executes that command with the selected line as argument.

    > ls | lines
         1	bar.txt
         2	foo.txt
         3	garply.txt
    > ls | lines 2
    foo.txt
    > ls | lines 2 cat
    Hello world!


## Example

I want run a python script from my kattis solutions, but I don't recall where it is exactly&#x2026;

    > find kattis -name "*.py" | lines
         1	kattis/different/different.py
         2	kattis/stretching/make_stretch.py
         3	kattis/primal/primes.py
         4	kattis/primal/make_primal.py
    > find kattis -name "*.py" | lines 2
    kattis/stretching/make_stretch.py
    > find kattis -name "*.py" | lines 2 python3
    helhellohellolohellohello

