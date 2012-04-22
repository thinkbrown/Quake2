ARCH := $(shell uname -m | sed -e s/i.86/i386/ -e s/sun4u/sparc/ -e s/sparc64/sparc/ -e s/arm.*/arm/ -e s/sa110/arm/ -e s/alpha/axp/)
CFLAGS = -c -I/usr/include/libxml2 -I./ -I../ -lxml2 
LDFLAGS = -lxml2 -pthread -I../
ODIR = q2map_$(ARCH)
CC = gcc
$(shell mkdir -p $(ODIR))

Q2MAPFILES = $(ODIR)/brushbsp.o $(ODIR)/bspfile.o $(ODIR)/cmdlib.o $(ODIR)/csg.o $(ODIR)/faces.o $(ODIR)/flow.o $(ODIR)/glfile.o $(ODIR)/l3dslib.o $(ODIR)/lbmlib.o $(ODIR)/leakfile.o $(ODIR)/lightmap.o $(ODIR)/main.o $(ODIR)/map.o $(ODIR)/mathlib.o $(ODIR)/md4.o $(ODIR)/nodraw.o $(ODIR)/patches.o $(ODIR)/path_init.o $(ODIR)/polylib.o $(ODIR)/portals.o $(ODIR)/prtfile.o $(ODIR)/qbsp.o $(ODIR)/qrad.o  $(ODIR)/qvis.o $(ODIR)/scriplib.o $(ODIR)/textures.o $(ODIR)/threads.o $(ODIR)/trace.o $(ODIR)/tree.o $(ODIR)/trilib.o $(ODIR)/writebsp.o $(ODIR)/inout.o

all:
	$(MAKE) q2map

q2map: $(Q2MAPFILES)
	$(CC) -o $(ODIR)/q2map $(LDFLAGS) $(Q2MAPFILES) -lm
$(ODIR)/brushbsp.o : brushbsp.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/bspfile.o : bspfile.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/cmdlib.o : cmdlib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/csg.o : csg.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/faces.o : faces.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/flow.o : flow.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/glfile.o : glfile.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/l3dslib.o : l3dslib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/lbmlib.o : lbmlib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/leakfile.o : leakfile.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/lightmap.o : lightmap.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/main.o : main.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/map.o : map.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/mathlib.o : mathlib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/md4.o : md4.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/nodraw.o : nodraw.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/patches.o : patches.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/path_init.o : path_init.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/polylib.o : polylib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/portals.o : portals.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/prtfile.o : prtfile.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/qbsp.o : qbsp.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/qrad.o : qrad.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/qvis.o : qvis.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/scriplib.o : scriplib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/textures.o : textures.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/threads.o : threads.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/trace.o : trace.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/tree.o : tree.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/trilib.o : trilib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/writebsp.o : writebsp.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/inout.o : inout.c
	cc $(CFLAGS) -o $@ $?
tidy:
	rm -f $(ODIR)/*.o

clean:
	rm -f $(ODIR)/*
	rm -r $(ODIR)
