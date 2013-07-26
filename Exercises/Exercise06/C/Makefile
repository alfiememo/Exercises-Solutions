#
# Matrix Multiply example makefile
#
# History: Written  by Tim mattson, August 2010
#          Modified by Tom Deakin and Simon McIntosh-Smith, October 2012
#          Modified by Tom Deakin, July 2013
#

CC=gcc

CCFLAGS=-O3 -lm -std=c99 -ffast-math

LIBS = -lOpenCL -fopenmp

COMMON_DIR = ../../C_common

MMUL_OBJS = matmul.o matrix_lib.o wtime.o err_code.o
EXEC = mult


all: $(EXEC)

mult: $(MMUL_OBJS)
	$(CC) $(MMUL_OBJS) $(CCFLAGS) $(LIBS) -o $(EXEC)

wtime.o: $(COMMON_DIR)/wtime.c
	$(CC) -c $^ $(CCFLAGS) $(LIBS) -o $@

err_code.o: $(COMMON_DIR)/err_code.c
	$(CC) -c $^ $(CCFLAGS) $(LIBS) -o $@

.c.o:
	$(CC) -c $< $(CCFLAGS) $(LIBS) -o $@

clean:
	rm -f $(MMUL_OBJS) $(EXEC)