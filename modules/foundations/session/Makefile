.PHONY: all
all: slides.pdf

SRC+=		preamble.tex
SRC+=		contents.tex

DEPENDS+= 	bibsp.sty

slides.pdf: slides.tex
slides.pdf: ${SRC}


.PHONY: clean
clean:
	${RM} slides.pdf


INCLUDE_MAKEFILES=../../../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
INCLUDE_BIBSP=../../../bibsp
include ${INCLUDE_BIBSP}/bibsp.mk
