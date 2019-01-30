OUT+= 	foundations.html


.PHONY: all
all: ${OUT}

foundations.md: security/security/README.md
foundations.md: security/scientific-method/README.md
foundations.md:
	${CAT} $^ > $@


.PHONY: clean
clean:
	${RM} ${OUT}


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk

