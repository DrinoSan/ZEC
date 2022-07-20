IDIR =../include

CC=gcc
CFLAGS=-I$(IDIR)
NAME=zec

ODIR=obj
LDIR =../lib

LIBS=-lm

_DEPS = chunk.h common.h memory.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = main.o chunk.o memory.o 
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))


$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

main: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~ 
