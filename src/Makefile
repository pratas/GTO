#============================================================================#
#                     GTO, IEETA/DETI, UNIVERSITY OF AVEIRO                  #
#============================================================================#
BIN    		= ../bin/
CC     		= gcc
CPLP   		= -ffast-math -msse2 #fgnu89-inline 
#-----------------------------------------------------------------------------
CFLAGS 		= -O3 -Wall $(CPLP)
#-----------------------------------------------------------------------------
LIBS   		= -lm
DEPS   		= defs.h
PROGS  	 	= $(BIN)/GTO \
         	  $(BIN)/GTO-Fastq2Fasta

OBJS     	= argparse.o buffer.o mem.o misc.o
#-----------------------------------------------------------------------------
all:
	$(MAKE) progs
progs: $(PROGS)
$(BIN)/GTO: GTO.c $(DEPS) $(OBJS) 
	$(CC) $(CFLAGS) -o $(BIN)/GTO GTO.c $(OBJS) $(LIBS)
$(BIN)/GTO-Fastq2Fasta: Fastq2Fasta.c $(DEPS) $(OBJS)
	$(CC) $(CFLAGS) -o $(BIN)/GTO-Fastq2Fasta Fastq2Fasta.c $(OBJS) $(LIBS)

argparse.o: argparse.c argparse.h $(DEPS)
	$(CC) -c $(CFLAGS) argparse.c
mem.o: mem.c mem.h $(DEPS)
	$(CC) -c $(CFLAGS) mem.c
misc.o: misc.c misc.h $(DEPS)
	$(CC) -c $(CFLAGS) misc.c
buffer.o: buffer.c buffer.h $(DEPS)
	$(CC) -c $(CFLAGS) buffer.c

##############################################################################
clean: 
	/bin/rm -f *.o
cleanall:
	/bin/rm -f *.o $(PROGS)
##############################################################################