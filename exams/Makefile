.PHONY: all
all: exam-160603.pdf exam-160822.pdf exam-161024.pdf

exam-161024.pdf: exam-161024.tex miunexam
exam-160822.pdf: exam-160822.tex miunexam
exam-160603.pdf: exam-160603.tex miunexam

all: exam-150604.pdf exam-150821.pdf exam-151030.pdf

exam-151030.pdf: exam-151030.tex literature.bib miunexam
exam-150821.pdf: exam-150821.tex literature.bib miunexam
exam-150604.pdf: exam-150604.tex literature.bib miunexam

all: exam-140603.pdf exam-140826.pdf exam-141028.pdf

exam-141028.pdf: exam-141028.tex literature.bib miunexam
exam-140826.pdf: exam-140826.tex literature.bib miunexam
exam-140603.pdf: exam-140603.tex literature.bib miunexam


EXAM_TAGS+= A C E

MODULE_QUESTION_DBs+=	infosak-questions.tex
EXAM_TAGS+=				foundations
EXAM_TAGS+=				infotheory crypto
EXAM_TAGS+=				auth
#EXAM_TAGS+=				ac refmon
EXAM_TAGS+=				usability
#EXAM_TAGS+=				fverif

MODULE_QUESTION_DBs+= 	../modules/accountability/overview/questions.tex
EXAM_TAGS+= 			accountability

MODULE_QUESTION_DBs+= 	../modules/software/overview/questions.tex
EXAM_TAGS+= 			software

MODULE_QUESTION_DBs+= 	../modules/trustcomp/overview/questions.tex
EXAM_TAGS+= 			trustcomp

MODULE_QUESTION_DBs+=	../modules/sidechannels/overview/questions.tex
EXAM_TAGS+=				sidechannels

EXAM_TAGS+=				passwd

questions.tex: ${MODULE_QUESTION_DBs}
	examgen -d ${MODULE_QUESTION_DBs} -t ${EXAM_TAGS} > $@


.PHONY: clean
clean:
	${RM} questions.tex


INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
