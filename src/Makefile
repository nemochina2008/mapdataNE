#-*- Makefile -*-

.SUFFIXES: .G .L .N .gon .line .name

CP = cp
ECHO = echo
RM = rm -f 
PKGNAME = mapdataNE
MKDIR = mkdir

GDATA = world10.G
LDATA = world10.L
NDATA = world10.N

.line.L:
	@$(MKDIR) -p ../inst/mapdata
	./Lmake 0 s b ${*}.line ${*}.linestats ../inst/mapdata/${*}.L

.gon.G:
	./Gmake b ${*}.gon ${*}.gonstats ../inst/mapdata/${*}.G ../inst/mapdata/${*}.L

.name.N:
	@$(MKDIR) -p ../inst/mapdata
	@$(CP) ${*}.name ../inst/mapdata/${*}.N

.PHONY: all gdata ldata ndata

all: gdata ndata

gdata: Gmake ldata
	$(MAKE) $(GDATA)

ldata: Lmake
	$(MAKE) $(LDATA)

ndata: 
	$(MAKE) $(NDATA)

clean:
	$(RM) Gmake Lmake ../inst/mapdata/* $(PKGNAME).s[lo] $(PKGNAME).dylib *.exe
	$(RM) -r ../inst/mapdata
