# $@ = target file
# $< = first dependency
# $^ = all dependencies

# detect all .o files based on their .c source

CC = gcc
INCLUDE_DIR = include
CFLAGS = -I$(INCLUDE_DIR)
C_SOURCES = $(wildcard src/*.c *.c )
DEPS = $(wildcard $(INCLUDE_DIR)/*.h *.h)
OBJ = ${C_SOURCES:.c=.o}

# First rule is the one executed when no parameters are fed to the Makefile


%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

server: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS)

clean:
	$(RM) src/*.bin src/*.o src/*.dis src/*.elf
	$(RM) lib/*.o
