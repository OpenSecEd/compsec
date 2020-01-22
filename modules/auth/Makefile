PUB_FILES+= 	auth.html
PUB_FILES+= 	pwdeval.pdf

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}


#auth.html: video.html reading.html session.html labs.html
auth.html: session.html labs.html
	pandoc -s \
		--metadata pagetitle="Authentication" \
		--metadata title="" \
		-o $@ $^

AUTH-README+= auth/intro/README.md
AUTH-README+= auth/bootstrapping/README.md
AUTH-README+= auth/user-machine/README.md
AUTH-README+= auth/something-you-know/README.md
AUTH-README+= auth/something-you-have/README.md
AUTH-README+= auth/machine-user/README.md

video.md: ${AUTH-README}
	${RM} $@
	echo "# Non-interactive learning sessions\n" >> $@
	for f in ${AUTH-README}; do ${CAT} $$f >> $@; echo >> $@; done

reading.html: reading.md auth.bib
	pandoc -s --bibliography=auth.bib -o $@ $<

#auth.tex: auth/intro/abstract.tex
#auth.tex: auth/bootstrapping/abstract.tex
#auth.tex: auth/user-machine/abstract.tex
#auth.tex: auth/something-you-know/abstract.tex
#auth.tex: auth/something-you-have/abstract.tex
#auth.tex: auth/machine-user/abstract.tex
#
#auth.tex:
#	${RM} auth.tex
#	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

auth.bib: auth/intro/intro.bib
auth.bib: auth/bootstrapping/bootstrapping.bib
auth.bib: auth/user-machine/user-machine.bib
auth.bib: auth/something-you-know/something-you-know.bib
auth.bib: auth/something-you-have/something-you-have.bib
auth.bib: auth/machine-user/machine-user.bib

auth.bib:
	${BIBTOOL} ${BIBTOOLFLAGS} -o $@ $^

pwdeval.pdf: auth/passwd/pwdeval/pwdeval.pdf
	${LN} $< $@

auth/%:
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: clean
clean:
	${RM} auth.md auth.html auth.bib
	${RM} pwdeval.pdf


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/tex.mk
