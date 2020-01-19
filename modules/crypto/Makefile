PUB_FILES+= 	crypto.html

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}

#crypto.html: video.html reading.html session.html
crypto.html: session.html
	pandoc -s \
		--metadata pagetitle="Crypto" \
		--metadata title="" \
		-o $@ $^

session.html: session.md
	${CONVERT.md.html}

CRYPTO_MODULES+= appliedcrypto/intro
CRYPTO_MODULES+= appliedcrypto/shared-key
CRYPTO_MODULES+= appliedcrypto/one-way
CRYPTO_MODULES+= appliedcrypto/pub-key
CRYPTO_MODULES+= appliedcrypto/zkp-smc
CRYPTO_MODULES+= appliedcrypto/sidechannels

video.md: infotheory/shannon-entropy/README.md
video.md: infotheory/applications/README.md
video.md: $(addsuffix /README.md,${CRYPTO_MODULES})

video.md:
	${RM} $@
	echo "# Non-interactive learning sessions\n" >> $@
	echo "## Elementary probability theory\n" >> $@
	${CAT} infotheory/probability/README.md >> $@
	echo >> $@
	echo "## Information theory\n" >> $@
	${CAT} infotheory/shannon-entropy/README.md >> $@
	echo >> $@
	${CAT} infotheory/applications/README.md >> $@
	echo >> $@
	echo "## High-level overview of crypto\n" >> $@
	for d in ${CRYPTO_MODULES}; do ${CAT} $$d/README.md >> $@; echo >> $@; done
	echo >> $@

reading.html: reading.md crypto.bib
	pandoc -s --bibliography=crypto.bib -o $@ $<


#crypto.tex: infotheory/shannon-entropy/abstract.tex
#crypto.tex: infotheory/applications/abstract.tex
#crypto.tex: appliedcrypto/overview/abstract.tex
#
#crypto.tex:
#	${RM} abstract.tex
#	echo "\\paragraph{Basic informatino theory}" >> $@
#	${CAT} infotheory/shannon-entropy/abstract.tex >> $@
#	echo "\\paragraph{Some applications of information theory}" >> $@
#	${CAT} infotheory/applications/abstract.tex >> $@
#	echo "\\paragraph{A high-level overview of crypto}" >> $@
#	${CAT} appliedcrypto/overview/abstract.tex >> $@

crypto.bib: infotheory/shannon-entropy/shannon-entropy.bib
crypto.bib: infotheory/applications/applications.bib
crypto.bib: $(addsuffix /bibliography.bib,${CRYPTO_MODULES})

crypto.bib:
	bibtool --preserve.key.case=on --print.deleted.entries=off -s -d -o $@ $^


infotheory/% appliedcrypto/%:
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: clean
clean:
	${RM} crypto.html
	${RM} crypto.bib
	${RM} video.md video.html reading.html session.html
	${MAKE} -C infotheory clean
	${MAKE} -C appliedcrypto clean

.PHONY: distclean
distclean:
	${MAKE} -C infotheory distclean
	${MAKE} -C appliedcrypto distclean


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
