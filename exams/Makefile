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


INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
