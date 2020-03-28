CC=g++
#$@ is the name of the file to be made, it is left side of the ":"
#$? is the names of the changed dependents.
hello: main.cpp hello.cpp factorial.cpp
	$(CC) $(CFLAGS) $? $(LDFLAGS) -o $@
#alternatively:
#hello: main.cpp hello.cpp factorial.cpp
#	$(CC) $(CFLAGS) $@.cpp $(LDFLAGS) -o $@

# $< the name of the related file that caused the action
# $* the prefix shared by target and dependent files
.cpp.o:
	$(CC) $(CFLAGS) -c $<

#Alternatively:
#.cpp.o:
#	$(CC) $(CFLAGS) -c $*.c

