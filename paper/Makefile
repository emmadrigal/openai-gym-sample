PROJECT = paper
LANG = es
SRC = $(wildcard *.tex)

.PHONY: all clean check

all: $(PROJECT).pdf

# MAIN LATEXMK RULE
$(PROJECT).pdf: $(SRC)
	latexmk -f -bibtex -use-make -pdf -pdflatex="pdflatex -synctex=1" $(PROJECT).tex

check: $(SRC)
	aspell --lang=$(LANG) -t -c $<

indent: $(SRC)
	latexindent -s -m --overwrite $<

clean:
	latexmk -C

