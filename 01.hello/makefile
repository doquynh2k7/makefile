##step1
##after ":", these files are depended for follow command
#hellomake: hellomake.c hellofunc.c
#	gcc -o hellomake hellomake.c hellofunc.c -I.

##step2 --------------------------------------
##define constants, arguments
#
#CC=gcc
#CFLAGS=-I.
#
#hellomake: hellomake.o hellofunc.o
#	$(CC) -o hellomake hellomake.o hellofunc.o

##step3 -----------------------------------------
##create dependences for header files "*.h" (if change, need to re-compile)
# -c flag says to generate the object file
# -o $@ says to put the output of the compilation in the file named on the left side of the :
# $< is the first item in the dependencies list
#
#CC=gcc
#CFLAGS=-I.
#DEPS = hellomake.h
#
#%.o: %.c $(DEPS)
#	$(CC) -c -o $@ $< $(CFLAGS)
#
#hellomake: hellomake.o hellofunc.o 
#	$(CC) -o hellomake hellomake.o hellofunc.o

#step4 ---------------------------------------
# $@ and $^, which are the left and right sides of the :
#
#CC=gcc
#CFLAGS=-I.
#DEPS = hellomake.h
#OBJ = hellomake.o hellofunc.o 
#
#%.o: %.c $(DEPS)
#	$(CC) -c -o $@ $< $(CFLAGS)
#
#hellomake: $(OBJ)
#	$(CC) -o $@ $^ $(CFLAGS)

##step5
#put header to include folder, objects to object folder
#some lib file in lib folder
#.PHONY rule keeps make from doing something with a file named clean 
#
IDIR =./include
CC=gcc
CFLAGS=-I$(IDIR)

ODIR=obj
LDIR =./lib

LIBS=-lm

_DEPS = hellomake.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = hellomake.o hellofunc.o 
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))


$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

hellomake: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~ 

