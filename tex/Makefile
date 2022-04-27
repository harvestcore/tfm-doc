DOC := proyecto.tex

all: doc

doc: $(DOC:.tex=.pdf)

all: proyecto.pdf

%.pdf: %.tex
	pdflatex $< && bibtex $* && pdflatex $< && pdflatex $<

spell:
	./check-spelling.sh

clean:
	rm -f **/*.pdf **/*.out **/*.lot **/*.log **/*.lof **/*.aux **/*.toc **/*.spellcheck **/*.toc **/*.rws