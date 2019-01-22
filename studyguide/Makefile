.PHONY: all
all: studyguide.pdf studyguide-slides.pdf

SRC=		studyguide.tex preamble.tex contents.tex
SRC+= 		schedule.tex ladok.tex hand-ins.tex late.tex
SRC+=		${MODULE_FILES}

MODULE_FILES+= 	foundations-lit.tex foundations.bib

foundations-lit.tex: ../modules/foundations/security/overview/abstract.tex
foundations.bib: ../modules/foundations/security/overview/overview.bib

MODULE_FILES+= 	usability-lit.tex usability.bib

usability-lit.tex: ../modules/foundations/usability/overview/abstract.tex
usability.bib: ../modules/foundations/usability/overview/overview.bib

MODULE_FILES+= 	infotheory-lit.tex infotheory.bib

infotheory-lit.tex: ../modules/crypto/infotheory/basics/abstract.tex
infotheory.bib: ../modules/crypto/infotheory/basics/basics.bib

MODULE_FILES+= 	crypto-lit.tex cryptomodule.bib

crypto-lit.tex: ../modules/crypto/appliedcrypto/overview/abstract.tex
cryptomodule.bib: ../modules/crypto/appliedcrypto/overview/overview.bib

MODULE_FILES+= 	auth-lit.tex authmodule.bib

auth-lit.tex: ../modules/auth/auth/overview/abstract.tex
authmodule.bib: ../modules/auth/auth/overview/overview.bib

MODULE_FILES+= 	fverif-lit.tex fverif.bib

fverif-lit.tex: ../modules/protocols/fverif/intro/abstract.tex
fverif.bib: ../modules/protocols/fverif/intro/intro.bib

MODULE_FILES+= 	accessctrl-lit.tex accessctrl.bib
#MODULE_FILES+= 	lvlltrl-lit.tex lvlltrl.bib
MODULE_FILES+= 	refmon-abstract.tex refmon.bib

accessctrl-lit.tex: ../modules/ac/ac/overview/abstract.tex
accessctrl.bib: ../modules/ac/ac/overview/overview.bib
#lvlltrl-lit.tex: ../modules/ac/ac/lvlltrl/abstract.tex
refmon-abstract.tex: ../modules/ac/ac/refmon/abstract.tex
refmon.bib: ../modules/ac/ac/refmon/refmon.bib

MODULE_FILES+= 	accountability-lit.tex accountability.bib

accountability-lit.tex: ../modules/accountability/accountability/overview/abstract.tex
accountability.bib: ../modules/accountability/accountability/overview/overview.bib

MODULE_FILES+= 	trustcomp-lit.tex trustcomp.bib

trustcomp-lit.tex: ../modules/trustcomp/trustcomp/overview/abstract.tex
trustcomp.bib: ../modules/trustcomp/trustcomp/overview/overview.bib

MODULE_FILES+= 	software-lit.tex software.bib

software-lit.tex: ../modules/software/software/overview/abstract.tex
software.bib: ../modules/software/software/overview/overview.bib

### Labs and seminars

MODULE_FILES+= 	security-society-abstract.tex security-society.bib

security-society-abstract.tex: ../modules/intro/ethics/security-society-seminar/abstract.tex
security-society.bib: ../modules/intro/ethics/security-society-seminar/security-society-seminar.bib

MODULE_FILES+= 	pricomlab-aim.tex pricomlab-lit.tex pricomlab.bib

pricomlab-aim.tex: ../modules/ac/pricomlab/aims.tex
pricomlab-lit.tex: ../modules/ac/pricomlab/literature.tex
pricomlab.bib: ../modules/ac/pricomlab/pricomlab.bib

MODULE_FILES+= 	pwdguess-aim.tex pwdguess-lit.tex pwdguess.bib

pwdguess-aim.tex: ../modules/auth/auth/passwd/pwdguess/aims.tex
pwdguess-lit.tex: ../modules/auth/auth/passwd/pwdguess/literature.tex
pwdguess.bib: ../modules/auth/auth/passwd/pwdguess/pwdguess.bib

MODULE_FILES+= 	pwdpolicies-aim.tex pwdpolicies-lit.tex pwdpolicies.bib

pwdpolicies-aim.tex: ../modules/auth/auth/passwd/pwdpolicies/aims.tex
pwdpolicies-lit.tex: ../modules/auth/auth/passwd/pwdpolicies/abstract.tex
pwdpolicies.bib: ../modules/auth/auth/passwd/pwdpolicies/pwdpolicies.bib

MODULE_FILES+= 	drm-abstract.tex drm.bib
MODULE_FILES+= 	stacksmash-abstract.tex stacksmash.bib
MODULE_FILES+= 	malware-abstract.tex malware.bib

drm-abstract.tex: ../modules/trustcomp/trustcomp/drmlab/literature.tex
drm.bib: ../modules/trustcomp/trustcomp/drmlab/drm.bib
stacksmash-abstract.tex: ../modules/software/software/stacksmashlab/literature.tex
stacksmash.bib: ../modules/software/software/stacksmashlab/stacksmash.bib
malware-abstract.tex: ../modules/software/software/malwarelab/literature.tex
malware.bib: ../modules/software/software/malwarelab/malware.bib

MODULE_FILES+= 	tools-abstract.tex tools.bib

tools-abstract.tex: ../modules/conclusion/tools/literature.tex
tools.bib: ../modules/conclusion/tools/tools.bib


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
