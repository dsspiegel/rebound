PROBLEMDIR=$(shell basename `dirname \`pwd\``)"/"$(shell basename `pwd`)
export OPENGL=1
export OPT=-O3

all:
	# Setup link to different modules
	ln -fs gravity_direct.c ../../src/gravity.c
	ln -fs boundaries_none.c ../../src/boundaries.c
	ln -fs integrator_ias15.c ../../src/integrator.c
	ln -fs collisions_none.c ../../src/collisions.c
	# Setup link to problem file
	ln -fs ../$(PROBLEMDIR)/problem.c ../../src/problem.c
	# Compile
	$(MAKE) -C ../../src/
	# Copy result
	cp ../../src/nbody .

doc: all
	$(MAKE) -C ../../src/ doc

clean:
	$(MAKE) -C ../../src/ clean
	rm -vf nbody
