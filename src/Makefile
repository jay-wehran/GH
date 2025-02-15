# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -Werror -std=c11 -I src/inc

# Target executable
TARGET = my_program

# Source files and object file mapping
SRCS = src/main.c src/core/menu.c
OBJS = $(SRCS:src/%.c=build/%.o)

# Default target
all: build $(TARGET)

# Create necessary directories
build:
	mkdir -p build build/core

# Build the executable
$(TARGET): $(OBJS)
	$(CC) $(OBJS) -o $(TARGET)

# Compile source files in src/ (like main.c)
build/%.o: src/%.c | build
	$(CC) $(CFLAGS) -c $< -o $@

# Compile source files in src/core/ (like menu.c)
build/core/%.o: src/core/%.c | build
	$(CC) $(CFLAGS) -c $< -o $@

# Clean build artifacts
clean:
	rm -rf build $(TARGET)
