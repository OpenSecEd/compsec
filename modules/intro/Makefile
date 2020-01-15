PUB_FILES+= 	intro.html
PUB_FILES+= 	security-society-seminar.pdf

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}

SECURITY-SOCIETY-FILES+= security-society-seminar.pdf
SECURITY-SOCIETY-FILES+= intro.tex
SECURITY-SOCIETY-FILES+= intro.bib

security-society-seminar.pdf: ethics/security-society-seminar/instructions.pdf
intro.tex: ethics/security-society-seminar/abstract.tex
intro.bib: ethics/security-society-seminar/security-society-seminar.bib

${SECURITY-SOCIETY-FILES}:
	ln -s $< $@

ethics/%:
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: clean
clean:
	${RM} intro.html ${SECURITY-SOCIETY-FILES}
	${MAKE} -C ethics clean

.PHONY: distclean
distclean:
	${MAKE} -C ethics distclean


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
