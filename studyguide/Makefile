.PHONY: all
all: studyguide.pdf studyguide-slides.pdf

SRC=		studyguide.tex preamble.tex contents.tex
SRC+= 		schedule.tex ladok.tex hand-ins.tex late.tex
SRC+=		${MODULE_FILES}

MODULE_FILES+= 	foundations-lit.tex foundations.bib

foundations-lit.tex: ../modules/foundations/overview/abstract.tex
foundations.bib: ../modules/foundations/overview/overview.bib

MODULE_FILES+= 	usability-lit.tex usability.bib

usability-lit.tex: ../modules/usability/overview/abstract.tex
usability.bib: ../modules/usability/overview/overview.bib

MODULE_FILES+= 	infotheory-lit.tex infotheory.bib

infotheory-lit.tex: ../modules/infotheory/basics/abstract.tex
infotheory.bib: ../modules/infotheory/basics/basics.bib

MODULE_FILES+= 	crypto-lit.tex cryptomodule.bib

crypto-lit.tex: ../modules/appliedcrypto/overview/abstract.tex
cryptomodule.bib: ../modules/appliedcrypto/overview/overview.bib

MODULE_FILES+= 	auth-lit.tex authmodule.bib

auth-lit.tex: ../modules/auth/overview/abstract.tex
authmodule.bib: ../modules/auth/overview/overview.bib

MODULE_FILES+= 	fverif-lit.tex fverif.bib

fverif-lit.tex: ../modules/fverif/intro/abstract.tex
fverif.bib: ../modules/fverif/intro/intro.bib

MODULE_FILES+= 	accessctrl-lit.tex accessctrl.bib
#MODULE_FILES+= 	lvlltrl-lit.tex lvlltrl.bib
MODULE_FILES+= 	refmon-abstract.tex refmon.bib

accessctrl-lit.tex: ../modules/ac/overview/abstract.tex
accessctrl.bib: ../modules/ac/overview/overview.bib
#lvlltrl-lit.tex: ../modules/ac/lvlltrl/abstract.tex
refmon-abstract.tex: ../modules/ac/refmon/abstract.tex
refmon.bib: ../modules/ac/refmon/refmon.bib

MODULE_FILES+= 	accountability-lit.tex accountability.bib

accountability-lit.tex: ../modules/accountability/overview/abstract.tex
accountability.bib: ../modules/accountability/overview/overview.bib

MODULE_FILES+= 	trustcomp-lit.tex trustcomp.bib

trustcomp-lit.tex: ../modules/trustcomp/overview/abstract.tex
trustcomp.bib: ../modules/trustcomp/overview/overview.bib

MODULE_FILES+= 	software-lit.tex software.bib

software-lit.tex: ../modules/software/overview/abstract.tex
software.bib: ../modules/software/overview/overview.bib

### Labs and seminars

MODULE_FILES+= 	pricomlab-aim.tex pricomlab-lit.tex pricomlab.bib

pricomlab-aim.tex: ../labs/pricomlab/aims.tex
pricomlab-lit.tex: ../labs/pricomlab/literature.tex
pricomlab.bib: ../labs/pricomlab/pricomlab.bib

MODULE_FILES+= 	pwdguess-aim.tex pwdguess-lit.tex pwdguess.bib

pwdguess-aim.tex: ../modules/auth/passwd/pwdguess/aims.tex
pwdguess-lit.tex: ../modules/auth/passwd/pwdguess/literature.tex
pwdguess.bib: ../modules/auth/passwd/pwdguess/pwdguess.bib

MODULE_FILES+= 	pwdpolicies-aim.tex pwdpolicies-lit.tex pwdpolicies.bib

pwdpolicies-aim.tex: ../modules/auth/passwd/pwdpolicies/aims.tex
pwdpolicies-lit.tex: ../modules/auth/passwd/pwdpolicies/abstract.tex
pwdpolicies.bib: ../modules/auth/passwd/pwdpolicies/pwdpolicies.bib

MODULE_FILES+= 	tools-abstract.tex tools.bib

tools-abstract.tex: ../labs/tools/literature.tex
tools.bib: ../labs/tools/tools.bib

MODULE_FILES+= 	drm-abstract.tex drm.bib
MODULE_FILES+= 	stacksmash-abstract.tex stacksmash.bib
MODULE_FILES+= 	malware-abstract.tex malware.bib

drm-abstract.tex: ../modules/trustcomp/drmlab/literature.tex
drm.bib: ../modules/trustcomp/drmlab/drm.bib
stacksmash-abstract.tex: ../modules/software/stacksmashlab/literature.tex
stacksmash.bib: ../modules/software/stacksmashlab/stacksmash.bib
malware-abstract.tex: ../modules/software/malwarelab/literature.tex
malware.bib: ../modules/software/malwarelab/malware.bib

MODULE_FILES+= 	ethics-lit.tex ethics.bib

ethics-lit.tex: ../modules/ethics/profession/literature.tex
ethics.bib: ../modules/ethics/profession/profession.bib


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
