#	Simple Makefile to generate a static library from all the 'c' files
#	in this directory
#
#	All that should be specified/edited is:
#       a. the name of this static library
#       b. any inter-dependencies to include
#
#   Author: Justyn Bell
#   Date  : 8/6/2014
#	

# The source files - all 'c' files in this directory
SRCS=*.c 

# The object files generated fromt he above 'c' files
OBJS=*.o

# Name of the static library (edit/name accordingly).
OUT=libospprocess.a

# Compile flag(s)
INCLUDE = -I../filter/ -I../afc/ -I../beam_forming -I../peak_detect -I../wdrc/ -I../common -I../array_utilities/
FLAGS=-L../filter/ -lospfilter -L../afc/ -lospafc -L../peak_detect -losppd -L../wdrc -lospwdrc -L../beam_forming -lospbeamform
CFLAGS= -Wall -Wextra

RM=rm
CC=gcc
AR=ar

all: generate_o_files archive_o_files

generate_o_files:
	@echo "***** Generating object (.o) files from source (.c) files...*****"
	$(CC) $(CFLAGS) $(INCLUDE) -c $(SRCS)

archive_o_files:
	@echo "***** Linking and archiving object (.o) files into $(OUT)... *****"
	$(AR) rcs $(OUT) $(OBJS)

clean:
	@echo "***** DONE! Cleaning up... *****"
	$(RM) *.o *.a

