PUB_FILES+= 	ac.html

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}

#ac.html: video.html reading.html session.html
ac.html: session.html
	pandoc -s \
		--metadata pagetitle="Access control" \
		--metadata title="" \
		-o $@ $^

video.md: ac/intro-ac/README.md
video.md: ac/ac-models/README.md
video.md: ac/multi-level/README.md
video.md: ac/multi-lateral/README.md

video.md:
	${RM} $@
	echo "# Non-interactive sessions\n" >> $@
	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

reading.html: reading.md ac.bib
	pandoc -s --bibliography=ac.bib -o $@ $<

#ac.tex: ac/overview/abstract.tex
#
#ac.tex:
#	${RM} ac.tex
#	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

ac.bib: ac.bib(ac/intro-ac/intro-ac.bib ac/ac-models/ac-models.bib)

ac.bib:
	bibtool --preserve.key.case=on --print.deleted.entries=off -s -d -o $@ $^


.PHONY: clean
clean:
	${RM} ac.html ac.bib
	${RM} video.md video.html reading.html session.html


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/tex.mk
