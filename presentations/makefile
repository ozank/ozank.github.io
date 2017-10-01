HTML_FILES= $(wildcard *.html)
PDF_FILES= $(HTML_FILES:.html=.pdf)

.SUFFIXES: .html .pdf

convert: $(PDF_FILES)

.html.pdf:
	wkhtmltopdf --load-error-handling "ignore" --load-media-error-handling "ignore" --page-width 111 --page-height 148 -B 0 -L 0 -R 0 -T 0 -O "Landscape" $< $@
