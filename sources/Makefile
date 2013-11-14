#
#  Compface OS/2 Makefile - Dimitris Michelinakis (michelinakis.gr/Dimitris)
#

NAME		= compface.exe
UNNAME		= uncompface.exe
LIBNAME		= libcompface.a
OBJECTS		= arith.o file.o compress.o gen.o uncompface.o
SOURCES		= compface.c uncompface.o arith.c file.c compress.c gen.c cmain.c uncmain.c
HDRS		= compface.h data.h

CC		= gcc
CDEFS		= $(SYSV)
CCOMP		= -g -DHAVE_FCNTL_H -DHAVE_STRERROR
#-Zsys -Zmt -Zomf
CFLAGS		= $(CDEFS) $(CCOMP)

all:		$(NAME) $(UNNAME)

$(NAME) :	cmain.o compface.o $(LIBNAME)
		$(CC) $(CFLAGS) -o $(NAME) cmain.o compface.o $(LIBNAME)

$(UNNAME) :	uncmain.o $(LIBNAME)
		$(CC) $(CFLAGS) -o $(UNNAME) uncmain.o $(LIBNAME)

$(LIBNAME) :	$(OBJECTS)
		ar rc $(LIBNAME) $(OBJECTS)
		-ranlib $(LIBNAME)

clean :
		rm -f *.o *.a *.sh core a.out $(NAME) $(UNNAME)

arith.o:	arith.c compface.h data.h
cmain.o:	cmain.c compface.h data.h
compface.o:	compface.c compface.h data.h
compress.o:	compress.c compface.h data.h
file.o:		file.c compface.h data.h
gen.o:		gen.c compface.h data.h
uncmain.o:	uncmain.c compface.h data.h
uncompface.o:	uncompface.c compface.h data.h
