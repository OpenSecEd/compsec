EXAM_TAGS+=		A C E

EXAM_DBS+=		infosak-questions.tex
EXAM_TAGS+=		foundations
EXAM_TAGS+=		infotheory crypto
EXAM_TAGS+=		auth
EXAM_TAGS+=		ac
#EXAM_TAGS+=		refmon
EXAM_TAGS+=		usability
#EXAM_TAGS+=		fverif

EXAM_DBS+= 		../modules/accountability/overview/questions.tex
EXAM_TAGS+= 	accountability

EXAM_DBS+= 		../modules/software/overview/questions.tex
EXAM_TAGS+= 	software

EXAM_DBS+= 		../modules/trustcomp/overview/questions.tex
EXAM_TAGS+= 	trustcomp

EXAM_DBS+=		../modules/sidechannels/overview/questions.tex
EXAM_TAGS+=		sidechannels

EXAM_TAGS+=		passwd


.PHONY: 2017
2017:			exam-170526.pdf exam-170830.pdf exam-180109.pdf
EXAM_IDS+=		170526 170330 180109

exam-170526.pdf: miunexam
exam-170830.pdf: miunexam
exam-180109.pdf: miunexam


.PHONY: 2016
2016: exam-160603.pdf exam-160822.pdf exam-161024.pdf

exam-161024.pdf: miunexam
EXAM_IDS+=		161024
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



INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/exam.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
