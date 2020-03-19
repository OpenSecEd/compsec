#PUB_FILES+= index.html

SUBDIR+= 	intro
SUBDIR+= 	foundations
SUBDIR+= 	crypto
SUBDIR+= 	auth
SUBDIR+= 	proto
SUBDIR+= 	ac
SUBDIR+= 	accountability
SUBDIR+= 	trustcomp
#SUBDIR+= 	software
SUBDIR+= 	conclusion

SUBDIR_GOALS= 	all clean distclean publish

PUB_SERVER?=ver.miun.se
PUB_DIR?= 	/srv/web/svn/courses/security/dasak
PUB_USER?=
PUB_GROUP?= svn


#index.md: $(foreach f,${SUBDIR},$f/$f.md)
#	${RM} $@
#	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done
#
#$(addsuffix /%,${SUBDIR}):
#	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: clean
clean:
	#${RM} index.md index.html
	$(foreach d,${SUBDIR},${MAKE} -C $d clean;)

.PHONY: distclean
distclean:
	$(foreach d,${SUBDIR},${MAKE} -C $d distclean;)


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/subdir.mk
include ${INCLUDE_MAKEFILES}/doc.mk
#include ${INCLUDE_MAKEFILES}/pub.mk
