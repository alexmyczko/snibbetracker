# Files to be compiled
SRC = CAllocator.c CEngine.c CInput.c CSynth.c dir_posix.c main.c
OBJ=$(SRC:.c=.o) # replaces the .c from SRC with .o

# Compiler
CC = gcc

RM=del

# Include paths
INCLUDE_PATHS = -I/usr/include/cjson

# Library paths
LIBRARY_PATHS = -L/usr/lib/x86_64-linux-gnu

# Compiler flags
COMPILER_FLAGS = -Wall -std=c99 -Wno-unused-function -g

# Linker flags
LINKER_FLAGS = -lSDL2main -lSDL2 -lm -lcjson -luuid

# Executable file
EXE = snibbetracker

# Compile command
#all: 
#	$(SRC)
#	$(CC) $(SRC) $(INCLUDE_PATHS) $(LIBRARY_PATHS) $(COMPILER_FLAGS) $(LINKER_FLAGS) -o $(EXE)

%.o: %.c         # combined w/ next line will compile recently changed .c files
	$(CC) $(COMPILER_FLAGS) $(INCLUDE_PATHS) -o $@ -c $<
	
.PHONY : all     # .PHONY ignores files named all
all: $(EXE)      # all is dependent on $(EXE) to be complete

$(EXE): $(OBJ)   # $(EXE) is dependent on all of the files in $(OBJ) to exist
	$(CC) $(OBJ) $(LIBRARY_PATHS) $(LINKER_FLAGS) -o $@

.PHONY : clean   # .PHONY ignores files named clean
clean:
	-$(RM) $(OBJ) $(EXE)
