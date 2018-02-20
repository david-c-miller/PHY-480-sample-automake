# PHY-480-sample-automake
A sample autoconf and automake system for the Project 2 sample code from PHY 480

## Information
The sample project was drafted up by David Miller (mill2723 at msu dot edu). If you have any questions or concerns they are likely best directed to him. It is licensed under the MIT License (please see LICENSE file for details).

## Using this project

In order to use this you need to go through the standard process for
initializing and compiling with autoconf and automake

1. First run `./autogen.sh` which contains the initialization commands for autoconf
2. Run `./configure` which runs autoconf using the configure.ac input file (take a look at what this is actually doing)
3. Run `make` to compile the program(s)

Optional: `make install` will typically install the compiled programs to /usr/local/bin or another default directory. This can be changed by passing a new directory to `./configure`

You can call `./configure --help` to view all options for autoconf. This can be useful for making custom compilation scripts on local machines with different compilers, linking options, or install paths.

## Prerequisites

I compiled and tested this on Ubuntu 16.04 running the following versions:
+ gcc       -   5.4.0
+ g++       -   5.4.0
+ gfortran  -   5.4.0
+ automake  -   1.15
+ autoconf  -   2.69
+ armadillo -   6.500.5
+ lapack    -   3.6.0
+ blas      -   3.6.0

These should not represent the minimum versions required to run this but your results *may* vary for different versions (both older and newer).
