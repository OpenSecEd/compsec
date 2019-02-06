OUT+= 	crypto.html


.PHONY: all
all: ${OUT}


CRYPTO.MD+= 	infotheory/probability/README.md
CRYPTO.MD+= 	infotheory/shannon-entropy/README.md
CRYPTO.MD+= 	infotheory/applications/README.md
CRYPTO.MD+= 	crypto.md

crypto.html: ${CRYPTO.MD}
	${CAT} ${CRYPTO.MD} | pandoc -f markdown -t html > $@


.PHONY: clean
clean:
	${RM} ${OUT}


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk

