.PHONY: all
all: studyguide.pdf studyguide-slides.pdf

SRC=		studyguide.tex preamble.tex contents.tex
SRC+= 		schedule.tex hand-ins.tex late.tex
SRC+=		${MODULE_FILES}

MODULE_FILES+= 	pricomlab-aim.tex pricomlab-lit.tex pricomlab.bib

pricomlab-aim.tex: ../modules/pricomlab/aims.tex
pricomlab-lit.tex: ../modules/pricomlab/literature.tex
pricomlab.bib: ../modules/pricomlab/pricomlab.bib

MODULE_FILES+= 	ismsmemo-aim.tex ismsmemo-lit.tex ismsmemo.bib
MODULE_FILES+= 	risksem-aim.tex risksem-lit.tex risksem.bib

ismsmemo-aim.tex: ../modules/ism/ismsmemo/aims.tex
ismsmemo-lit.tex: ../modules/ism/ismsmemo/abstract.tex
ismsmemo.bib: ../modules/ism/ismsmemo/ismsmemo.bib
risksem-aim.tex: ../modules/ism/risksem/aims.tex
risksem-lit.tex: ../modules/ism/risksem/abstract.tex
risksem.bib: ../modules/ism/risksem/risksem.bib

MODULE_FILES+= 	msbintro-lit.tex msbintro.bib
MODULE_FILES+= 	msbforts-lit.tex msbforts.bib

msbintro-lit.tex: ../modules/ism/msbframework/msbintro/literature.tex
msbintro.bib: ../modules/ism/msbframework/msbintro/msbintro.bib
msbforts-lit.tex: ../modules/ism/msbframework/msbforts/literature.tex
msbforts.bib: ../modules/ism/msbframework/msbforts/msbforts.bib

MODULE_FILES+=	recmgmt-abstract.tex recmgmt.bib

recmgmt-abstract.tex: ../modules/ism/recmgmt/abstract.tex
recmgmt.bib: ../modules/ism/recmgmt/recmgmt.bib

MODULE_FILES+= 	crypto-lit.tex cryptomodule.bib

crypto-lit.tex: ../modules/appliedcrypto/overview/abstract.tex
cryptomodule.bib: ../modules/appliedcrypto/overview/overview.bib

MODULE_FILES+= 	software-lit.tex software.bib

software-lit.tex: ../modules/software/overview/abstract.tex
software.bib: ../modules/software/overview/overview.bib

MODULE_FILES+= 	usability-lit.tex usability.bib

usability-lit.tex: ../modules/usability/overview/abstract.tex
usability.bib: ../modules/usability/overview/overview.bib

MODULE_FILES+= 	infotheory-lit.tex infotheory.bib

infotheory-lit.tex: ../modules/infotheory/basics/abstract.tex
infotheory.bib: ../modules/infotheory/basics/basics.bib

MODULE_FILES+= 	trustcomp-lit.tex trustcomp.bib

trustcomp-lit.tex: ../modules/trustcomp/overview/abstract.tex
trustcomp.bib: ../modules/trustcomp/overview/overview.bib

MODULE_FILES+= 	fverif-lit.tex fverif.bib

fverif-lit.tex: ../modules/fverif/intro/abstract.tex
fverif.bib: ../modules/fverif/intro/intro.bib

MODULE_FILES+= 	auth-lit.tex authmodule.bib

auth-lit.tex: ../modules/auth/overview/abstract.tex
authmodule.bib: ../modules/auth/overview/overview.bib

MODULE_FILES+= 	pwdguess-aim.tex pwdguess-lit.tex pwdguess.bib

pwdguess-aim.tex: ../modules/auth/passwd/pwdguess/aims.tex
pwdguess-lit.tex: ../modules/auth/passwd/pwdguess/literature.tex
pwdguess.bib: ../modules/auth/passwd/pwdguess/pwdguess.bib

MODULE_FILES+= 	pwdpolicies-aim.tex pwdpolicies-lit.tex pwdpolicies.bib

pwdpolicies-aim.tex: ../modules/auth/passwd/pwdpolicies/aims.tex
pwdpolicies-lit.tex: ../modules/auth/passwd/pwdpolicies/abstract.tex
pwdpolicies.bib: ../modules/auth/passwd/pwdpolicies/pwdpolicies.bib

MODULE_FILES+= 	accessctrl-lit.tex accessctrl.bib
#MODULE_FILES+= 	lvlltrl-lit.tex lvlltrl.bib

accessctrl-lit.tex: ../modules/ac/overview/abstract.tex
accessctrl.bib: ../modules/ac/overview/overview.bib
#lvlltrl-lit.tex: ../modules/ac/lvlltrl/abstract.tex

MODULE_FILES+= 	foundations-lit.tex foundations.bib

foundations-lit.tex: ../modules/foundations/overview/abstract.tex
foundations.bib: ../modules/foundations/overview/overview.bib

MODULE_FILES+= 	accountability-lit.tex accountability.bib

accountability-lit.tex: ../modules/accountability/overview/abstract.tex
accountability.bib: ../modules/accountability/overview/overview.bib

MODULE_FILES+= 	project-aim.tex

project-aim.tex: ../modules/research/prestudy/aims.tex


${MODULE_FILES}:
	ln -s $^ $@


studyguide.pdf: ${SRC}
studyguide.pdf: bibsp.sty assessment.sty

studyguide-slides.pdf: ${SRC}
studyguide-slides.pdf: bibsp.sty assessment.sty


.PHONY: clean
clean:
	${RM} studyguide.pdf studyguide-slides.pdf

.PHONY: clean-depends distclean
clean-depends distclean:
	${RM} ${MODULE_FILES}
	${RM} llncs2e.zip
	${RM} bibsp.sty
	${RM} -R biblatex-lncs-src


### INCLUDES ###

INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
INCLUDE_BIBSP=../bibsp
include ${INCLUDE_BIBSP}/bibsp.mk
INCLUDE_BIBEDU=../bibedu
include ${INCLUDE_BIBEDU}/bibedu.mk
