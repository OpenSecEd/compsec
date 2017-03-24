.PHONY: all
all: studyguide.pdf

SRC+=		studyguide-preamble.tex studyguide-contents.tex
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

MODULE_FILES+= 	crypto-lit.tex crypto.bib

crypto-lit.tex: ../modules/appliedcrypto/overview/abstract.tex
crypto.bib: ../modules/appliedcrypto/overview/overview.bib

MODULE_FILES+=	spuriouslab-lit.tex spuriouslab-aim.tex spuriouslab.bib

spuriouslab-aim.tex: ../modules/appliedcrypto/spuriouslab/aims.tex
spuriouslab-lit.tex: ../modules/appliedcrypto/spuriouslab/abstract.tex
spuriouslab.bib: ../modules/appliedcrypto/spuriouslab/spuriouslab.bib

MODULE_FILES+= 	pricomlab-aim.tex pricomlab-lit.tex pricomlab.bib

pricomlab-aim.tex: ../labs/pricomlab/aims.tex
pricomlab-lit.tex: ../labs/pricomlab/literature.tex
pricomlab.bib: ../labs/pricomlab/pricomlab.bib

MODULE_FILES+= 	auth-lit.tex auth.bib

auth-lit.tex: ../modules/auth/overview/abstract.tex
auth.bib: ../modules/auth/overview/overview.bib

MODULE_FILES+= 	pwdguess-aim.tex pwdguess-lit.tex pwdguess.bib

pwdguess-aim.tex: ../modules/auth/passwd/pwdguess/aims.tex
pwdguess-lit.tex: ../modules/auth/passwd/pwdguess/literature.tex
pwdguess.bib: ../modules/auth/passwd/pwdguess/pwdguess.bib

MODULE_FILES+= 	pwdpolicies-aim.tex pwdpolicies-lit.tex pwdpolicies.bib

pwdpolicies-aim.tex: ../modules/auth/passwd/pwdpolicies/aims.tex
pwdpolicies-lit.tex: ../modules/auth/passwd/pwdpolicies/literature.tex
pwdpolicies.bib: ../modules/auth/passwd/pwdpolicies/pwdpolicies.bib

MODULE_FILES+= 	accessctrl-lit.tex ac.bib
MODULE_FILES+= 	lvlltrl-lit.tex lvlltrl.bib

accessctrl-lit.tex: ../modules/ac/overview/abstract.tex
accessctrl.bib: ../modules/ac/overview/overview.bib
lvlltrl-lit.tex: ../modules/ac/lvlltrl/abstract.tex
lvlltrl.bib: ../modules/ac/lvlltrl/lvlltrl.bib

MODULE_FILES+= 	refmon-lit.tex refmon.bib

refmon-lit.tex: ../modules/ac/refmon/abstract.tex
refmon.bib: ../modules/ac/refmon/refmon.bib

#MODULE_FILES+= 	unix-lit.tex unix.bib
#
#unix-lit.tex: ../modules/ac/unix/literature.tex
#unix.bib: ../modules/ac/unix/unix.bib
#
#MODULE_FILES+= 	windows-lit.tex windows.bib
#
#windows-lit.tex: ../modules/ac/windows/literature.tex
#windows.bib: ../modules/ac/windows/windows.bib

MODULE_FILES+= 	accountability-lit.tex accountability.bib

accountability-lit.tex: ../modules/accountability/overview/abstract.tex
accountability.bib: ../modules/accountability/overview/overview.bib

#MODULE_FILES+= 	database-lit.tex database.bib
#
#database-lit.tex: ../modules/database/overview/literature.tex
#database.bib: ../modules/database/overview/database.bib

MODULE_FILES+=	tools-aim.tex tools-lit.tex tools.bib

tools-aim.tex: ../labs/tools/aims.tex
tools-lit.tex: ../labs/tools/literature.tex
tools.bib: ../labs/tools/tools.bib

MODULE_FILES+= 	trustcomp-lit.tex trustcomp.bib

trustcomp-lit.tex: ../modules/trustcomp/overview/abstract.tex
trustcomp.bib: ../modules/trustcomp/overview/overview.bib

MODULE_FILES+=	drm-aim.tex drm-lit.tex drm.bib

drm-aim.tex: ../modules/trustcomp/drmlab/aims.tex
drm-lit.tex: ../modules/trustcomp/drmlab/literature.tex
drm.bib: ../modules/trustcomp/drmlab/drm.bib

MODULE_FILES+= 	sidechannels-lit.tex sidechannels.bib

sidechannels-lit.tex: ../modules/sidechannels/overview/abstract.tex
sidechannels.bib: ../modules/sidechannels/overview/overview.bib

MODULE_FILES+= 	software-lit.tex software.bib

software-lit.tex: ../modules/software/overview/abstract.tex
software.bib: ../modules/software/overview/overview.bib

MODULE_FILES+=	stacksmash-aim.tex stacksmash-lit.tex stacksmash.bib

stacksmash-aim.tex: ../modules/software/stacksmashlab/aims.tex
stacksmash-lit.tex: ../modules/software/stacksmashlab/literature.tex
stacksmash.bib: ../modules/software/stacksmashlab/stacksmash.bib

MODULE_FILES+=	malware-aim.tex malware-lit.tex malware.bib

malware-aim.tex: ../modules/software/malwarelab/aims.tex
malware-lit.tex: ../modules/software/malwarelab/literature.tex
malware.bib: ../modules/software/malwarelab/malware.bib

MODULE_FILES+= 	ethics-aim.tex ethics-lit.tex ethics.bib

ethics-aim.tex: ../modules/ethics/profession/aims.tex
ethics-lit.tex: ../modules/ethics/profession/literature.tex
ethics.bib: ../modules/ethics/profession/profession.bib


${MODULE_FILES}:
	ln -s $^ $@


studyguide.pdf: studyguide.tex ${SRC}
studyguide.pdf: lncs


.PHONY: clean-depends
clean-depends:
	${RM} ${MODULE_FILES}


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
