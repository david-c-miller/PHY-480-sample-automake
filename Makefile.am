## Start of sample automake file
## Created by David Miller

## this tells make what file types you'll be using
SUFFIXES = .c .h .cpp

## this declares what files make can clean up for you, in additional to what
## it already cleans
## I normally just add any backup files (filename.ext~)
CLEANFILES = *~ src/*~

#################
##   SUBDIRS   ##
#################

## this declares sub directories that you want compiled that already
## contain Makefiles

## I normally name this file makefile (lowercase) to differentiate it from
## the automake Makefiles

## It **MUST** contain a dummy 'all' and clean' statements for automake
## to find it and work with it (see the end of the makefiles here)
## additionally, any automake make 'xyz' statements will need dummy references
## here (for example) make distclean is very useful and you can define
## 'distclean: clean'

SUBDIRS = src/UnitTestscpp/JacobiTests src/UnitTestscpp/ToeplitzTests

#################
## C/C++ FLAGS ##
#################

## CC is the C compiler while CXX is the C++ compiler
## you only need to declare whichever you're using
CC=gcc
CXX=g++

## I like to include extra warnings but you can choose to remove this
WARN_FLAGS = -Wall -Wextra

## AM_CFLAGS are the additonal flags for C while AM_CXXFLAGS are for C++
AM_CXXFLAGS = $(WARN_FLAGS) $(O_FLAG_0) -Isrc

## this declares any linking libraries
## for example in C you may want to link the math and core libraries
# LDADD = -lm -lc
LDADD = -larmadillo -llapack -lblas

############################
## LIBRARIES AND BINARIES ##
############################

## bin_PROGRAMS defines all binaries that need to be built
bin_PROGRAMS = bin/TridiagToeplitz.x

## you can declare multiple programs here as long as each one has it's
## own source listing below

########################
## HEADERS AND SOURCE ##
########################

## for bin/TridiagToeplitz.x we need to define bin_TridiagToeplitz_x_SOURCES
## which is the sources for the binary
## **NOTE** the bin_ leading term is because of the bin/ directory choice
bin_TridiagToeplitz_x_SOURCES = src/TridiagToeplitz.cpp

## you can have multiple source listings (one per binary) with however many
## source/header files required for the final binary to be compiled and linked

#############################
## OTHER OPTIONS AND FLAGS ##
#############################

## I declare the following different O Flag options which I use
## You can customize this or just always use the same
## I normally use O_FLAG_0 for development and O_FLAG_3 for deployment
O_FLAG_0 = -g3 -pg -O0
O_FLAG_1 = -g1 -pg -O1
O_FLAG_2 = -O2
O_FLAG_3 = -O3
