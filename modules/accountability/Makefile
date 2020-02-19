PUB_FILES+= 	accountability.html

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}


accountability.html: video.html reading.html session.html
	pandoc -s \
		--metadata pagetitle="Accountability" \
		--metadata title="" \
		-o $@ $^

video.md: accountability/book-keeping/README.md
video.md: accountability/logging/README.md

video.md:
	${RM} $@
	echo "# Non-interactive sessions\n" >> $@
	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

reading.html: reading.md accountability.bib
	pandoc -s --bibliography=accountability.bib -o $@ $<

#accountability.tex: accountability/overview/abstract.tex
#
#accountability.tex:
#	${RM} $@
#	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

accountability.bib: accountability/book-keeping/book-keeping.bib
accountability.bib: accountability/logging/logging.bib

accountability.bib:
	bibtool --preserve.key.case=on --print.deleted.entries=off -s -d -o $@ $^


.PHONY: clean
clean:
	${RM} video.md video.html reading.html session.html
	${RM} accountability.bib


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/tex.mk
