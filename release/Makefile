PUB_FILES?=		${DOCUMENTS} ${HTML}
PUB_SERVER?=	ver.miun.se
PUB_DIR?=		/srv/web/svn/courses/security/dasak
PUB_USER?=		
PUB_GROUP?=		svn
PUB_METHOD?=	ssh
PUB_VCS?=		git
PUB_AUTOTAG?=	true

.PHONY: all
all: ${DOCUMENTS} ${HTML}

### Lectures

DOCUMENTS+=	studyguide.pdf studyguide-slides.pdf
SRC-studyguide.pdf=../studyguide/studyguide.pdf
SRC-studyguide-slides.pdf=../studyguide/studyguide-slides.pdf

DOCUMENTS+=	foundations-slides.pdf
SRC-foundations-slides.pdf=../modules/foundations/overview/overview.pdf

DOCUMENTS+=	usability-slides.pdf
SRC-usability-slides.pdf=../modules/usability/overview/overview.pdf

DOCUMENTS+=	infotheory-slides.pdf
SRC-infotheory-slides.pdf=../modules/infotheory/basics/basics.pdf

DOCUMENTS+=	crypto-slides.pdf
SRC-crypto-slides.pdf=../modules/appliedcrypto/overview/overview-slides.pdf

DOCUMENTS+=	auth-slides.pdf
SRC-auth-slides.pdf=../modules/auth/overview/overview.pdf

DOCUMENTS+=	ac-slides.pdf
SRC-ac-slides.pdf=../modules/ac/overview/slides.pdf

DOCUMENTS+=	refmon-slides.pdf
SRC-refmon-slides.pdf=../modules/ac/refmon/slides.pdf

DOCUMENTS+=	accountability-slides.pdf
SRC-accountability-slides.pdf=../modules/accountability/overview/slides.pdf

DOCUMENTS+=	trustcomp-slides.pdf
SRC-trustcomp-slides.pdf=../modules/trustcomp/overview/overview.pdf

DOCUMENTS+=	software-slides.pdf
SRC-software-slides.pdf=../modules/software/overview/overview-slides.pdf

### Assignments

DOCUMENTS+=	security-society-seminar.pdf security-society-slides.pdf
SRC-security-society-seminar.pdf=../modules/ethics/security-society-seminar/notes.pdf
SRC-security-society-slides.pdf=../modules/ethics/security-society-seminar/slides.pdf

DOCUMENTS+=	pwdguess.pdf
SRC-pwdguess.pdf=../modules/auth/passwd/pwdguess/pwdguess.pdf

DOCUMENTS+=	pwdpolicies.pdf
SRC-pwdpolicies.pdf=../modules/auth/passwd/pwdpolicies/pwdpolicies.pdf

DOCUMENTS+=	pricomlab.pdf
SRC-pricomlab.pdf=../labs/pricomlab/pricomlab.pdf

DOCUMENTS+=	toolslab.pdf
SRC-toolslab.pdf=../labs/tools/tools.pdf

DOCUMENTS+=	drmlab.pdf
SRC-drmlab.pdf=../modules/trustcomp/drmlab/drm.pdf

DOCUMENTS+=	stacksmashlab.pdf
SRC-stacksmashlab.pdf=../modules/software/stacksmashlab/stacksmash.pdf

DOCUMENTS+=	malwarelab.pdf
SRC-malwarelab.pdf=../modules/software/malwarelab/malware.pdf

### Learning platform

HTML+= introduction.html
SRC-introduction.html=../learning-platform/introduction.html

HTML+= foundations-usability.html
SRC-foundations-usability.html=../learning-platform/foundations-usability.html

HTML+= infotheory-crypto.html
SRC-infotheory-crypto.html=../learning-platform/infotheory-crypto.html

HTML+= auth.html
SRC-auth.html=../learning-platform/auth.html

HTML+= ac.html
SRC-ac.html=../learning-platform/ac.html

HTML+= accountability.html
SRC-accountability.html=../learning-platform/accountability.html

HTML+= trustcomp.html
SRC-trustcomp.html=../learning-platform/trustcomp.html

HTML+= software.html
SRC-software.html=../learning-platform/software.html

HTML+= conclusion.html
SRC-conclusion.html=../learning-platform/conclusion.html

HTML+= index.html
SRC-index.html=../learning-platform/index.html


.PHONY: print
print: ${DOCUMENTS}


.PHONY: clean distclean
clean:
	${RM} ${DOCUMENTS} ${HTML}

define target_rules
all: $(1)

$(1): ${SRC-$(1)}
	cp $$^ $$@

${SRC-$(1)}::
	${MAKE} -C $$(dir $$@) $$(notdir $$@)

clean: clean-$(1)
clean-$(1):
	${MAKE} -C $$(dir ${SRC-$(1)}) clean

distclean: distclean-$(1)
distclean-$(1):
	${MAKE} -C $$(dir ${SRC-$(1)}) distclean clean-depends
endef

$(foreach target,${DOCUMENTS} ${HTML},$(eval $(call target_rules,${target})))


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/doc.mk
