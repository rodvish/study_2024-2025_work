makefile

all: report.pdf report.docx

report.pdf: report.md
	pandoc report.md -o report.pdf \
	--resource-path=.:image \
	--pdf-engine=xelatex \
	-V mainfont="Liberation Serif" \
	-V sansfont="Liberation Sans" \
	-V monofont="Liberation Mono" \
	-V geometry:margin=2.5cm

report.docx: report.md
	pandoc report.md -o report.docx \
	--resource-path=.:image

clean:
	rm -f report.pdf report.docx

.PHONY: all clean
