ARCH := $(shell uname -m | sed -e s/i.86/i386/ -e s/sun4u/sparc/ -e s/sparc64/sparc/ -e s/arm.*/arm/ -e s/sa110/arm/ -e s/alpha/axp/)
CFLAGS = -c -I../common 
LDFLAGS =
ODIR = ../build_$(ARCH)/qdata
EXEBASE = qdata
EXE = $(ODIR)/qdata
CC = gcc


FILES = $(ODIR)/qdata.o $(ODIR)/models.o $(ODIR)/sprites.o $(ODIR)/images.o  $(ODIR)/cmdlib.o $(ODIR)/scriplib.o $(ODIR)/lbmlib.o $(ODIR)/mathlib.o $(ODIR)/l3dslib.o $(ODIR)/trilib.o $(ODIR)/threads.o $(ODIR)/tables.o $(ODIR)/video.o $(ODIR)/bspfile.o $(ODIR)/mdfour.o

all:
	mkdir -p ../build_$(ARCH)
	mkdir -p $(ODIR)
	$(MAKE) build

build : $(FILES)
	$(CC) -o $(EXE) $(LDFLAGS) $(FILES) -lm	
$(ODIR)/qdata.o : qdata.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/models.o : models.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/sprites.o : sprites.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/images.o : images.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/tables.o : tables.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/video.o : video.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/cmdlib.o : ../common/cmdlib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/scriplib.o : ../common/scriplib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/lbmlib.o : ../common/lbmlib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/mathlib.o : ../common/mathlib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/trilib.o : ../common/trilib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/l3dslib.o : ../common/l3dslib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/threads.o : ../common/threads.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/bspfile.o : ../common/bspfile.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/mdfour.o : ../common/mdfour.c
	$(CC) $(CFLAGS) -o $@ $?
clean:
	rm -f $(ODIR)/*.o $(ODIR)/$(EXEBASE)
	rm -r $(ODIR)
