ARCH := $(shell uname -m | sed -e s/i.86/i386/ -e s/sun4u/sparc/ -e s/sparc64/sparc/ -e s/arm.*/arm/ -e s/sa110/arm/ -e s/alpha/axp/)
CFLAGS = -c -I../../common 
LDFLAGS =
ODIR = ../../build_$(ARCH)/bspinfo
EXEBASE = bspinfo
EXE = $(ODIR)/bspinfo
CC = gcc

FILES = $(ODIR)/bspinfo3.o $(ODIR)/bspfile.o $(ODIR)/cmdlib.o $(ODIR)/scriplib.o

all:
	mkdir ../../build_$(ARCH)
	mkdir -p $(ODIR)
	$(MAKE) build

build : $(FILES)
	cc -o $(EXE) $(LDFLAGS) $(FILES)
$(ODIR)/bspinfo3.o : bspinfo3.c
	cc $(CFLAGS) -o $@ $? 
$(ODIR)/cmdlib.o : ../../common/cmdlib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/scriplib.o : ../../common/scriplib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/bspfile.o : ../../common/bspfile.c
	cc $(CFLAGS) -o $@ $?

clean:
	rm -f $(ODIR)/*.o $(ODIR)/$(EXEBASE)
	rm -r $(ODIR)
