# File: Standard Makefile for CSC415
#
# Description - This make file should be used for all your projects
# It should be modified as needed for each homework
#
# ROOTNAME should be set you your lastname_firstname_HW.  Except for
# and group projects, this will not change throughout the semester
#
# HW should be set to the assignment number (i.e. 1, 2, 3, etc.)
#
# FOPTION can be set to blank (nothing) or to any thing starting with an 
# underscore (_).  This is the suffix of your file name.
#
# With these three options above set your filename for your homework
# assignment will look like:  bierman_robert_HW1_main.c 
#
# RUNOPTIONS can be set to default values you want passed into the program
# this can also be overridden on the command line
#
# OBJ - You can append to this line for additional files necessary for
# your program, but only when you have multiple files.  Follow the convention
# but hard code the suffix as needed.
#
# To Use the Makefile - Edit as above
# then from the command line run:  make
# That command will build your program, and the program will be named the same
# as your main c file without an extension.
#
# You can then execute from the command line: make run
# This will actually run your program
#
# Using the command: make clean
# will delete the executable and any object files in your directory.
#

VOLUMENAME=SampleVolume
VOLUMESIZE=10000000
BLOCKSIZE=512
CC=gcc
CFLAGS= -g -lm -lreadline -I.
LIBS =pthread
DEPS = 
ADDOBJ= fsLow.o b_io.o mfs.o VCB.o bitMap.o

%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS) 
all:
	make fsshell
	make Formater
	make Tester

fsshell: fsshell.o $(ADDOBJ)
	$(CC) -o $@ $^ $(CFLAGS) -lm -l readline -l $(LIBS)

Formater: Formater.o $(ADDOBJ)
	$(CC) -o $@ $^ $(CFLAGS) -lm -l readline -l $(LIBS)

Tester: Tester.o $(ADDOBJ)
	$(CC) -o $@ $^ $(CFLAGS) -lm -l readline -l $(LIBS)

clean:
	rm *.o fsshell Tester Formater

test:
	make Tester
	./Tester $(VOLUMENAME)

format:
	make Formater
	./Formater $(VOLUMENAME) $(VOLUMESIZE) $(BLOCKSIZE)

run:
	make fsshell
	./fsshell $(VOLUMENAME)

wipe:
	rm $(VOLUMENAME)

