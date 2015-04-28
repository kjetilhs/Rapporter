TEX = pdflatex -shell-escape -interaction=nonstopmode -file-line-error
PRE =  $(TEX) -ini -job-name="preamble"b "&pdflatex preamble.tex\dump"
BIB = bibtex

.PHONY: all view

all : main.pdf

view :
	open main.pdf

main.pdf : main.tex main.bbl main.blg
	$(TEX) main.tex

main.bbl main.blg : main.bib main.aux
	$(BIB) main

main.aux : main.tex
	$(TEX) main.tex

main.bib : main.tex
	$(TEX) main.tex


# .PHONY: all auto ex3-report.pdf



# all: ex3-report.pdf

# auto:
# 	while true; do \
# 		$(MAKE); \
# 		inotifywait -e close_write -r main.tex bib.tex sections/ fig/; \
# 	done;

# ex3-report.pdf:
# 	xelatex -halt-on-error -shell-escape -jobname=$(basename $@) main.tex
