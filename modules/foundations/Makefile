PUB_FILES+= 	foundations.html
PUB_FILES+= 	foundations-session.pdf

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}

foundations.html: foundations.md
	pandoc -s \
		--metadata pagetitle="Foundations" \
		--metadata title="" \
		-o $@ $^

foundations.md: session.md
foundations.md: security.md
foundations.md: attacking-humans.md psychology.md
foundations.md: scientific-method.md

foundations.md:
	${RM} $@
	for f in $^; do ${CAT} $$f >> $@; echo '\n\n' >> $@; done

security.md: security/security/README.md
scientific-method.md: security/scientific-method/README.md
attacking-humans.md: usability/attacking-humans/README.md
psychology.md: usability/psychology/README.md

security.md scientific-method.md attacking-humans.md psychology.md:
	${LN} $< $@


.PHONY: all
all: foundations.tex foundations.bib

foundations.tex: security/security/abstract.tex
foundations.tex: security/scientific-method/abstract.tex
foundations.tex: usability/attacking-humans/abstract.tex
foundations.tex: usability/psychology/abstract.tex

foundations.tex:
	${RM} $@
	echo "\\paragraph{What is security?}" >> $@
	cat security/security/abstract.tex >> $@
	echo "\\paragraph{The scientific method}" >> $@
	cat security/scientific-method/abstract.tex >> $@
	echo "\\paragraph{Attacking humans}" >> $@
	cat usability/attacking-humans/abstract.tex >> $@
	echo "\\paragraph{Psychology}" >> $@
	cat usability/psychology/abstract.tex >> $@

foundations.bib: security/security/security.bib
foundations.bib: security/scientific-method/scientific-method.bib
foundations.bib: usability/attacking-humans/bibliography.bib
foundations.bib: usability/psychology/bibliography.bib

foundations.bib:
	${BIBTOOL} ${BIBTOOLFLAGS} -o $@ $^

foundations-session.pdf: session/slides.pdf
	${LN} $^ $@


session/% security/% usability/%:
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: clean
clean:
	${RM} foundations.html foundations.md
	${RM} security.md scientific-method.md attacking-humans.md psychology.md
	${RM} foundations.tex foundations.bib
	${RM} foundations-session.pdf
	${MAKE} -C security clean
	${MAKE} -C usability clean
	${MAKE} -C session clean

.PHONY: distclean
distclean:
	${MAKE} -C security distclean
	${MAKE} -C usability distclean
	${MAKE} -C session distclean


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/tex.mk
