EXAM_NAME= 		DT145G

YEARS+= 		2020
EXAM_IDS-2020+= 200320

EXAM_DATE-200320= 	2020-03-20


YEARS+= 		2019
EXAM_IDS-2019+= 190322
EXAM_IDS-2019+= 190612
EXAM_IDS-2019+= 190827

EXAM_DATE-190322= 	2019-03-22
EXAM_DATE-190612= 	2019-06-12
EXAM_DATE-190827= 	2019-08-27


YEARS+= 		2018
EXAM_IDS-2018= 	180607 180827 190109

EXAM_DATE-180607= 	2018-06-07
EXAM_DATE-180827= 	2018-08-27
EXAM_DATE-190109= 	2019-01-09


YEARS+= 		2017
EXAM_IDS-2017=	170526 170830 180109

${EXAM_NAME}-170526.pdf: miunexam
${EXAM_NAME}-170830.pdf: miunexam
${EXAM_NAME}-180109.pdf: miunexam


YEARS+= 		2016
EXAM_IDS-2016= 	160603 160822 161024

${EXAM_NAME}-161024.pdf: questions-161024.tex miunexam
${EXAM_NAME}-160822.pdf: ${EXAM_NAME}-160822.tex miunexam
${EXAM_NAME}-160603.pdf: ${EXAM_NAME}-160603.tex miunexam


YEARS+= 		2015
EXAM_IDS-2015= 	150604 150821 151030

${EXAM_NAME}-151030.pdf: ${EXAM_NAME}-151030.tex miunexam
${EXAM_NAME}-150821.pdf: ${EXAM_NAME}-150821.tex miunexam
${EXAM_NAME}-150604.pdf: ${EXAM_NAME}-150604.tex miunexam


YEARS+= 		2014
EXAM_IDS-2014= 	140603 140826 141028

${EXAM_NAME}-141028.pdf: ${EXAM_NAME}-141028.tex miunexam
${EXAM_NAME}-140826.pdf: ${EXAM_NAME}-140826.tex miunexam
${EXAM_NAME}-140603.pdf: ${EXAM_NAME}-140603.tex miunexam


.PHONY: all
all: ${YEARS}

-include individuals.mk


EXAM_FLAGS?=	-NCi

EXAM_TAGS+=		A C E

#EXAM_DBS+=		infosak-questions.tex

# Questions databases from learning modules

EXAM_DBS+=      $(shell find ../modules -name \*.tex)

EXAM_TAGS+= 	foundations
EXAM_TAGS+=		usability
EXAM_TAGS+=		infotheory
EXAM_TAGS+=		crypto
EXAM_TAGS+=		auth passwd
EXAM_TAGS+=		ac
EXAM_TAGS+= 	accountability
EXAM_TAGS+= 	trustcomp
EXAM_TAGS+= 	software
#EXAM_TAGS+=		sidechannels

# Questions databases from previously generated exams

EXAM_DBS+=		$(foreach id,${EXAM_IDS}, ${EXAM_QNAME}-${id}.tex)
#EXAM_DBS+=		${EXAM_QNAME}-161024.tex
#EXAM_DBS+= 		${EXAM_NAME}-160822.tex
#EXAM_DBS+= 		${EXAM_NAME}-160603.tex
#EXAM_DBS+=		${EXAM_NAME}-151030.tex
#EXAM_DBS+= 		${EXAM_NAME}-150821.tex
#EXAM_DBS+= 		${EXAM_NAME}-150604.tex
#EXAM_DBS+=		${EXAM_NAME}-141028.tex
#EXAM_DBS+= 		${EXAM_NAME}-140826.tex
#EXAM_DBS+= 		${EXAM_NAME}-140603.tex


PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/dasak/exams
PUB_FILES?= 	$(foreach id,$(foreach y,${YEARS}, ${EXAM_IDS-$y}), ${EXAM_NAME}-${id}.pdf)


### Generate targets for all years ###

define exam_id_template=
.PHONY: $(1)
EXAM_IDS+= 		${EXAM_IDS-$(1)}
$(1): 			$(foreach d,${EXAM_IDS-$(1)}, ${EXAM_NAME}-$d.pdf)

.PHONY: clean clean-$(1)
clean: clean-$(1)
clean-$(1):
	${RM} $(foreach d,${EXAM_IDS-$(1)}, ${EXAM_NAME}-$d.pdf)
endef

$(foreach y,${YEARS},$(eval $(call exam_id_template,$y)))


### Don't expect questions-%.tex for exams from before 2017 ###

$(foreach exam_id,$(foreach y,2014 2015 2016, ${EXAM_IDS-$y}),\
	$(eval EXAM_QNAME-${exam_id}=${EXAM_NAME}))


### All exams depends on literature.bib ###

${EXAM_NAME}-%.pdf: literature.bib

literature.bib: $(shell find ../ -name \*.bib)
	bibtool --preserve.key.case=on --print.deleted.entries=off -s -d -o $@ $^


.PHONY: clean
clean:
	${RM} literature.bib


INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/exam.mk
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
