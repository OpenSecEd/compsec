PUB_FILES+= 	conclusion.html
PUB_FILES+= 	tools.pdf

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}

conclusion.html: conclusion.md

conclusion.bib:
	touch $@

tools.pdf: tools/tools.pdf
	${LN} $< $@

tools/%:
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: clean
clean:
	${RM} ${PUB_FILES}
	${MAKE} -C tools clean

.PHONY: distclean
distclean:
	${MAKE} -C tools distclean


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk

