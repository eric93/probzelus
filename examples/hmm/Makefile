PROBZELUC=probzeluc

ZLI=$(wildcard *.zli)
ZCI=$(ZLI:zli=zci)

NAME=hmm
NAME_DS=hmm_ds


all: build

$(NAME).ml main.ml: $(ZCI) $(NAME).zls
	$(PROBZELUC) -s main $(NAME).zls

$(NAME_DS).ml main_ds.ml: $(ZCI) $(NAME_DS).zls
	$(PROBZELUC) -s main_ds $(NAME_DS).zls

clean:
	rm -f $(NAME).ml main.ml
	rm -f $(NAME_DS).ml main_ds.ml
	rm -f *.zci

## Generic rules

.phony: build exec

exec: main.ml main_ds.ml
	dune exec ./main.exe

exec_ds: main.ml main_ds.ml
	dune exec ./main_ds.exe

build: main.ml main_ds.ml
	dune build main.exe

%.zci: %.zli
	$(PROBZELUC) $<

cleanall: clean
	dune clean
	rm -f *~
