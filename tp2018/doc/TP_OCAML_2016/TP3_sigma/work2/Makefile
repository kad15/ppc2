SOURCES = tp3.ml
EXEC = tp3
CAMLC = ocamlc -I ./lib
CAMLDEP = ocamldep
LIBS = 
#unix.cma graphics.cma maze.cmo 

all: depend $(EXEC)

OBJS = $(SOURCES:.ml=.cmo)

$(EXEC): $(OBJS)
	$(CAMLC) -o $(EXEC) $(LIBS) $(OBJS)

.SUFFIXES: .ml .mli .cmi .cmo .cmx

.mli.cmi:
	$(CAMLC) -c $<

.ml.cmo:
	$(CAMLC) -c $<

clean:
	rm -f *.cm[iox] *~ .*~ *.o #*#
	rm -f $(EXEC)

.depend: $(SOURCES)
	$(CAMLDEP) *.mli *.ml > .depend

depend: $(SOURCES)
	$(CAMLDEP) *.mli *.ml > .depend

include .depend

