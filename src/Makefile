IDIR =../include

CC=gcc
CFLAGS=-I$(IDIR) -std=c11
NAME=zec

ODIR=obj
LDIR =../lib

LIBS=-lm

_DEPS = chunk.h common.h memory.h debug.h value.h vm.h compiler.h scanner.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = main.o chunk.o memory.o  debug.o value.o vm.o compiler.o scanner.o
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))


$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

main: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~ 
