.PHONY: 2017
2017:			exam-170526.pdf exam-170830.pdf exam-180109.pdf
EXAM_IDS+=		170526 170830 180109

exam-170526.pdf: miunexam
exam-170830.pdf: miunexam
exam-180109.pdf: miunexam


.PHONY: 2016
2016: exam-160603.pdf exam-160822.pdf exam-161024.pdf

exam-161024.pdf: questions-161024.tex miunexam
exam-160822.pdf: exam-160822.tex miunexam
exam-160603.pdf: exam-160603.tex miunexam


.PHONY: 2015
2015: exam-150604.pdf exam-150821.pdf exam-151030.pdf

exam-151030.pdf: exam-151030.tex literature.bib miunexam
exam-150821.pdf: exam-150821.tex literature.bib miunexam
exam-150604.pdf: exam-150604.tex literature.bib miunexam


.PHONY: 2014
2014: exam-140603.pdf exam-140826.pdf exam-141028.pdf

exam-141028.pdf: exam-141028.tex literature.bib miunexam
exam-140826.pdf: exam-140826.tex literature.bib miunexam
exam-140603.pdf: exam-140603.tex literature.bib miunexam



EXAM_TAGS+=		A C E

EXAM_DBS+=		infosak-questions.tex
EXAM_TAGS+=		passwd

# Questions databases from learning modules

#EXAM_DBS+=		../modules/foundations/overview/questions.tex
EXAM_TAGS+=		foundations

#EXAM_DBS+=		../modules/infotheory/basics/questions.tex
EXAM_TAGS+=		infotheory

#EXAM_DBS+=		../modules/appliedcrypto/overview/questions.tex
EXAM_TAGS+=		crypto

#EXAM_DBS+=		../modules/auth/overview/questions.tex
EXAM_TAGS+=		auth

EXAM_DBS+=		../modules/ac/overview/questions.tex
EXAM_TAGS+=		ac

#EXAM_DBS+=		../modules/ac/refmon/questions.tex
#EXAM_TAGS+=		refmon

#EXAM_DBS+=		../modules/usability/overview/questions.tex
EXAM_TAGS+=		usability

#EXAM_DBS+=		../modules/fverif/intro/questions.tex
#EXAM_TAGS+=		fverif

EXAM_DBS+= 		../modules/accountability/overview/questions.tex
EXAM_TAGS+= 	accountability

EXAM_DBS+= 		../modules/software/overview/questions.tex
EXAM_TAGS+= 	software

EXAM_DBS+= 		../modules/trustcomp/overview/questions.tex
EXAM_TAGS+= 	trustcomp

EXAM_DBS+=		../modules/sidechannels/overview/questions.tex
EXAM_TAGS+=		sidechannels

# Questions databases from previously generated exams

#EXAM_DBS+=		$(foreach id,${EXAM_IDS}, questions-${id}.tex)
EXAM_DBS+=		questions-170526.tex
EXAM_DBS+=		questions-161024.tex exam-160822.tex exam-160603.tex
EXAM_DBS+=		exam-151030.tex exam-150821.tex exam-150604.tex
EXAM_DBS+=		exam-141028.tex exam-140826.tex exam-140603.tex



INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/exam.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
