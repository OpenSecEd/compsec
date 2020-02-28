PUB_FILES+= 	trustcomp.html

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}

#trustcomp.html: video.html
#trustcomp.html: reading.html session.html
trustcomp.html: session.html
trustcomp.html:
	pandoc -s \
		--metadata pagetitle="Trusted computing" \
		--metadata title="" \
		-o $@ $^

video.md: trustcomp/drm/README.md
video.md: trustcomp/overview/README.md

video.md:
	${RM} $@
	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

trustcomp.tex: trustcomp/overview/abstract.tex
	${CAT} $^ > $@

trustcomp.bib: trustcomp/drm/bibliography.bib
trustcomp.bib: trustcomp/overview/bibliography.bib

trustcomp.bib:
	bibtool --preserve.key.case=on --print.deleted.entries=off -s -d -o $@ $^


.PHONY: clean
clean:
	${RM} trustcomp.html
	${RM} video.md video.html reading.html session.html
	${RM} trustcomp.bib


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/tex.mk
