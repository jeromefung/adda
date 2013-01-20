# Makefile for pip. Uses the default gfortran, which should be present on any Unix. Other
# compilers and optimization flags may also be used - should be adjusted below.

CF      = gfortran
FFLAGS  = -O3 -ffast-math -funroll-loops
FSOURCE = FEM-Geo-Wr.f90 geometry.f90 ivread_wr.f90 limits_cor3.f90 point-inside-polyhedron.f90
PROG    = pip

FOBJECTS   := $(FSOURCE:.f90=.o)

#===================================================================================================

.PHONY: all clean

all: $(PROG)

$(PROG): $(FOBJECTS) Makefile
	$(CF) -o $@ $(FOBJECTS)

$(FOBJECTS): %.o: %.f90 Makefile
	$(CF) -c $(FFLAGS) $<

clean:
	rm -f *.o $(PROG) $(PROG).exe