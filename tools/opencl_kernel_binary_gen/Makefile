# Basic "command" variables
CC = gcc
RM = rm -f

# Setup OCLROOT
ifdef NVIDIA_CUDA
OCLROOT = $(NVIDIA_CUDA)
else
OCLROOT = /usr/local/cuda
endif

ifdef AMDAPPSDKROOT
AMDAPP = -DAMDAPPSDK
OCLROOT = $(AMDAPPSDKROOT)
endif

ifdef ATISTREAMSDKROOT
AMDAPP = -DAMDAPPSDK
OCLROOT = $(ATISTREAMSDKROOT)
endif

# gcc options
CFLAGS = -Wall -I'$(OCLROOT)/include'
LDFLAGS = -L'$(OCLROOT)/lib/x86' -lOpenCL
CFILES = binary_gen.c
        
# Executable path
BINARY_GEN = ../../run/binary_gen

default:
	$(CC) $(CFILES) $(CFLAGS) $(LDFLAGS) -o $(BINARY_GEN) 

clean:
	$(RM) $(BINARY_GEN)