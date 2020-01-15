OUT+= 	foundations.html

SUBDIR+=security/security
SUBDIR+=security/scientific-method
SUBDIR+=usability/attacking-humans
SUBDIR+=usability/psychology

SUBDIR_GOALS=all clean distclean


.PHONY: all
all: ${OUT}

foundations.md: security/security/README.md
foundations.md: security/scientific-method/README.md
foundations.md: usability/attacking-humans/README.md
foundations.md: usability/psychology/README.md

foundations.md:
	${CAT} $^ > $@


.PHONY: all
all: abstract.tex abstract.bib

abstract.tex: security/security/abstract.tex
abstract.tex: security/scientific-method/abstract.tex
abstract.tex: usability/overview/abstract.tex

abstract.tex:
	${RM} abstract.tex
	echo "\\paragraph{What is security?}" >> abstract.tex
	cat security/security/abstract.tex >> abstract.tex
	echo "\\paragraph{The scientific method}" >> abstract.tex
	cat security/scientific-method/abstract.tex >> abstract.tex
	echo "\\subsection{Usability}" >> abstract.tex
	cat usability/overview/abstract.tex >> abstract.tex

abstract.bib: security/security/security.bib
abstract.bib: security/scientific-method/scientific-method.bib
abstract.bib: usability/overview/overview.bib

abstract.bib:
	${CAT} $^ > $@


.PHONY: clean
clean:
	${RM} ${OUT}
	${RM} abstract.tex


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/subdir.mk
