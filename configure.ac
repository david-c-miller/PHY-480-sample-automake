############################################################
## initialization for autoconf
## this declares the project name, version, owner, and prefix
AC_INIT(
	[PHY480 Automake Example],
	[1.0.0],
	[mill2723@msu.edu],
    [phy480-automake-example])
############################################################

############################################################
## initialize automake

## I'm declaring that I may use non-standard files (foreign) and that I
## will have subdirectories (subdir-objects)

## You may need to change this for non Linux systems

AM_INIT_AUTOMAKE([subdir-objects foreign])
#############################################################

#############################################################
## this declares the type of program
## AC_PROG_CC is for C programs
## AC_PROG_CXX is for C++

AC_PROG_CXX

## this just checks that you can pass -c and -o to the compiler
AC_PROG_CXX_C_O

## this declares the language as C++ (defaults to C otherwise)
AC_LANG(C++)
#############################################################

#############################################################
## the declares the minimum version of autoconf
AC_PREREQ([2.59])
#############################################################

#############################################################
## this can be used to check for headers used in the program

AC_CHECK_HEADERS([cmath] [iostream] [fstream] [iomanip],,AC_MSG_ERROR(Standard library headers are required))
AC_CHECK_HEADERS([armadillo],,AC_MSG_ERROR(Armadillo is used for matrix operations))
#############################################################

#############################################################
## this can be used to check if the linked libraries are present
## AC_SEARCH_LIBS is used for C libraries

#AC_SEARCH_LIBS([sqrt],[m],,AC_MSG_ERROR(Math library is required))

## Search for BLAS and LAPACK (actually Fortran libraries so we temporarily
## switch to searching in Fortran with AC_LANG_PUSH and AC_LANG_POP

AC_LANG_PUSH([Fortran])
AC_SEARCH_LIBS([sgetrf], [lapack],,AC_MSG_ERROR(LAPACK library is required))
AC_SEARCH_LIBS([drotg], [blas],,AC_MSG_ERROR(BLAS library is required))
AC_LANG_POP([Fortran])

## C++ is a little harder :(
## this basically creates a test compilation to check if armadillo is installed

AC_LINK_IFELSE(
  [AC_LANG_PROGRAM([#include <armadillo>],
    [arma::mat dummy])],
  [TEST_LIBS="-larmadillo"] [HAVE_ARMADILLO=1],
  [AC_MSG_WARN([Armadillo is not installed.])]
 )
#############################################################

#############################################################
## this statement is required if you want to build any linkable
## libraries

#AC_PROG_RANLIB
#############################################################

#############################################################
## this declares what output you want autoconf to generate, in this case we
## want a Makefile
AC_CONFIG_FILES([Makefile])

## Final statement
AC_OUTPUT
#############################################################
