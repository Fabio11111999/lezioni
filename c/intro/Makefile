# Makefile for Constrained Persistent Perfect Phylogeny
CC = gcc
SOURCES := $(wildcard *.c)

CFLAGS_STD = -g -Wall -DDEBUG -O3 -march=native -Wno-deprecated -Wno-parentheses -Wno-format
STD_LIBS = glib-2.0

CFLAGS_EXTRA =  -std=c11 -Wshadow -Wpointer-arith -Wcast-qual -Wstrict-prototypes -Wmissing-prototypes
CFLAGS_LIBS = `pkg-config --cflags $(STD_LIBS)`
LDLIBS = `pkg-config --libs $(STD_LIBS)`
CFLAGS = $(CFLAGS_STD) $(CFLAGS_EXTRA) $(CFLAGS_LIB)
OBJECTS = $(SOURCES:%.c=%.o)
CC_FULL = $(CC) $(CFLAGS) $(CFLAGS_LIBS)

bin: $(OBJECTS)

%.o: %.c
	@echo '* Compiling $<'
	$(CC_FULL) -o $@ $<  $(LDLIBS)

clean:
	@echo "Cleaning..."
	rm -rf  *.o

.PHONY: clean
