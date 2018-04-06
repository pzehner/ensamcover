.PHONY: all build extract clean

all: build extract

build:
	latexmk -xelatex -pdf sample.tex

extract:
	convert -density 40 "sample.pdf[0]" -alpha remove -quality 90 sample-front.jpg
	convert -density 40 "sample.pdf[2]" -alpha remove -quality 90 sample-rear.jpg

clean:
	latexmk -C
