ARCH := $(shell uname -m | sed -e s/i.86/i386/ -e s/sun4u/sparc/ -e s/sparc64/sparc/ -e s/arm.*/arm/ -e s/sa110/arm/ -e s/alpha/axp/)
CFLAGS = -c -Icommon -I/usr/include/libxml2
LDFLAGS =
ODIR = build_$(ARCH)
CC = gcc
$(shell mkdir -p $(ODIR))

QDATAFILES = $(ODIR)/qdata.o $(ODIR)/models.o $(ODIR)/sprites.o $(ODIR)/images.o  $(ODIR)/cmdlib.o $(ODIR)/scriplib.o $(ODIR)/lbmlib.o $(ODIR)/mathlib.o $(ODIR)/l3dslib.o $(ODIR)/trilib.o $(ODIR)/threads.o $(ODIR)/tables.o $(ODIR)/video.o $(ODIR)/bspfile.o $(ODIR)/mdfour.o

BSPINFOFILES = $(ODIR)/bspinfo3.o $(ODIR)/bspfile.o $(ODIR)/cmdlib.o $(ODIR)/scriplib.o

QBSP3FILES = $(ODIR)/brushbsp.o $(ODIR)/bspfile.o $(ODIR)/cmdlib.o $(ODIR)/faces.o $(ODIR)/nodraw.o $(ODIR)/glfile.o $(ODIR)/leakfile.o $(ODIR)/map.o $(ODIR)/mathlib.o $(ODIR)/polylib.o $(ODIR)/portals.o $(ODIR)/prtfile.o $(ODIR)/qbsp3.o $(ODIR)/scriplib.o $(ODIR)/textures.o $(ODIR)/threads.o $(ODIR)/tree.o $(ODIR)/writebsp.o $(ODIR)/csg.o

QRAD3FILES = $(ODIR)/bspfile.o $(ODIR)/cmdlib.o $(ODIR)/lbmlib.o $(ODIR)/mathlib.o $(ODIR)/scriplib.o $(ODIR)/polylib.o $(ODIR)/qrad3.o $(ODIR)/threads.o $(ODIR)/trace.o $(ODIR)/lightmap.o $(ODIR)/patches.o

QVIS3FILES = $(ODIR)/bspfile.o $(ODIR)/cmdlib.o $(ODIR)/mathlib.o $(ODIR)/scriplib.o  $(ODIR)/threads.o $(ODIR)/qvis3.o $(ODIR)/flow.o


all:
	$(MAKE) qdata
	$(MAKE) bspinfo
	$(MAKE) qbsp3
	$(MAKE) qvis3
#	$(MAKE) qrad3


qdata: $(QDATAFILES)
	$(CC) -o $(ODIR)/qdata $(LDFLAGS) $(QDATAFILES) -lm	
bspinfo: $(BSPINFOFILES)
	cc -o $(ODIR)/bspinfo $(LDFLAGS) $(BSPINFOFILES) -lm
qbsp3 : $(QBSP3FILES)
	cc -o $(ODIR)/qbsp3 $(LDFLAGS) $(QBSP3FILES) -lm
qvis3 : $(QVIS3FILES)
	cc -o $(ODIR)/qvis3 $(LDFLAGS) $(QVIS3FILES) -lmm
#qrad3 : $(QRAD3FILES)
#	cc -o $(ODIR)/qrad3 $(LDFLAGS) $(QRAD3FILES) -lm

$(ODIR)/cmdlib.o : common/cmdlib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/scriplib.o : common/scriplib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/lbmlib.o : common/lbmlib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/mathlib.o : common/mathlib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/trilib.o : common/trilib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/l3dslib.o : common/l3dslib.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/threads.o : common/threads.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/bspfile.o : common/bspfile.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/mdfour.o : common/mdfour.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/polylib.o : common/polylib.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/qdata.o : qdata/qdata.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/models.o : qdata/models.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/sprites.o : qdata/sprites.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/images.o : qdata/images.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/tables.o : qdata/tables.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/video.o : qdata/video.c
	$(CC) $(CFLAGS) -o $@ $?
$(ODIR)/bspinfo3.o : bsp/bspinfo3/bspinfo3.c
	cc $(CFLAGS) -o $@ $? 
$(ODIR)/brushbsp.o : bsp/qbsp3/brushbsp.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/faces.o : bsp/qbsp3/faces.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/nodraw.o : bsp/qbsp3/nodraw.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/glfile.o : bsp/qbsp3/glfile.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/leakfile.o : bsp/qbsp3/leakfile.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/map.o : bsp/qbsp3/map.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/portals.o : bsp/qbsp3/portals.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/prtfile.o : bsp/qbsp3/prtfile.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/qbsp3.o : bsp/qbsp3/qbsp3.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/tree.o : bsp/qbsp3/tree.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/textures.o : bsp/qbsp3/textures.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/writebsp.o : bsp/qbsp3/writebsp.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/csg.o : bsp/qbsp3/csg.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/qrad3.o : bsp/qrad3/qrad3.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/patches.o : bsp/qrad3/patches.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/trace.o : bsp/qrad3/trace.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/vismat.o : bsp/qrad3/vismat.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/lightmap.o : bsp/qrad3/lightmap.c
	cc $(CFLAGS) -o $@ $?
# NOTE: MISSING "vismat.c"
$(ODIR)/qvis3.o : bsp/qvis3/qvis3.c
	cc $(CFLAGS) -o $@ $?
$(ODIR)/flow.o : bsp/qvis3/flow.c
	cc $(CFLAGS) -o $@ $?

tidy:
	rm -f $(ODIR)/*.o

clean:
	rm -f $(ODIR)/*
	rm -r $(ODIR)
