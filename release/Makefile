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

DOCUMENTS+=	foundations-security-slides.pdf
SRC-foundations-security-slides.pdf=../modules/foundations/security/security/security.pdf

DOCUMENTS+=	foundations-scientific-method-slides.pdf
SRC-foundations-scientific-method-slides.pdf=../modules/foundations/security/scientific-method/scientific-method.pdf

DOCUMENTS+=	usability-attacking-humans-slides.pdf
SRC-usability-slides.pdf=../modules/foundations/usability/attacking-humans/attacking-humans.pdf

DOCUMENTS+=	usability-psychology-slides.pdf
SRC-usability-psychology-slides.pdf=../modules/foundations/usability/psychology/psychology.pdf

DOCUMENTS+=	infotheory-slides.pdf
SRC-infotheory-slides.pdf=../modules/crypto/infotheory/basics/basics.pdf

DOCUMENTS+=	crypto-slides.pdf
SRC-crypto-slides.pdf=../modules/crypto/appliedcrypto/overview/overview-slides.pdf

DOCUMENTS+=	auth-slides.pdf
SRC-auth-slides.pdf=../modules/auth/auth/overview/overview.pdf

DOCUMENTS+= protocols-slides.pdf
SRC-protocols-slides.pdf=../modules/protocols/fverif/intro/intro.pdf

DOCUMENTS+=	ac-slides.pdf
SRC-ac-slides.pdf=../modules/ac/ac/overview/slides.pdf

DOCUMENTS+=	refmon-slides.pdf
SRC-refmon-slides.pdf=../modules/ac/ac/refmon/slides.pdf

DOCUMENTS+=	accountability-slides.pdf
SRC-accountability-slides.pdf=../modules/accountability/accountability/overview/slides.pdf

DOCUMENTS+=	trustcomp-slides.pdf
SRC-trustcomp-slides.pdf=../modules/trustcomp/trustcomp/overview/overview.pdf

DOCUMENTS+=	software-slides.pdf
SRC-software-slides.pdf=../modules/software/software/overview/overview-slides.pdf

### Assignments

DOCUMENTS+=	security-society-seminar.pdf security-society-slides.pdf
SRC-security-society-seminar.pdf=../modules/intro/ethics/security-society-seminar/notes.pdf
SRC-security-society-slides.pdf=../modules/intro/ethics/security-society-seminar/slides.pdf

DOCUMENTS+=	pwdguess.pdf
SRC-pwdguess.pdf=../modules/auth/auth/passwd/pwdguess/pwdguess.pdf

DOCUMENTS+=	pwdpolicies.pdf
SRC-pwdpolicies.pdf=../modules/auth/auth/passwd/pwdpolicies/pwdpolicies.pdf

DOCUMENTS+=	pricomlab.pdf
SRC-pricomlab.pdf=../modules/ac/pricomlab/pricomlab.pdf

DOCUMENTS+=	drm.pdf
SRC-drm.pdf=../modules/trustcomp/trustcomp/drmlab/drm.pdf

DOCUMENTS+=	stacksmash.pdf
SRC-stacksmash.pdf=../modules/software/software/stacksmashlab/stacksmash.pdf

DOCUMENTS+=	malware.pdf
SRC-malware.pdf=../modules/software/software/malwarelab/malware.pdf

DOCUMENTS+=	tools.pdf
SRC-tools.pdf=../modules/conclusion/tools/tools.pdf

### Learning platform

HTML+= intro.html
SRC-intro.html=../modules/intro/intro.html

HTML+= foundations.html
SRC-foundations.html=../modules/foundations/foundations.html

HTML+= crypto.html
SRC-crypto.html=../modules/crypto/crypto.html

HTML+= auth.html
SRC-auth.html=../modules/auth/auth.html

HTML+= protocols.html
SRC-protocols.html=../modules/protocols/protocols.html

HTML+= ac.html
SRC-ac.html=../modules/ac/ac.html

HTML+= accountability.html
SRC-accountability.html=../modules/accountability/accountability.html

HTML+= trustcomp.html
SRC-trustcomp.html=../modules/trustcomp/trustcomp.html

HTML+= software.html
SRC-software.html=../modules/software/software.html

HTML+= conclusion.html
SRC-conclusion.html=../modules/conclusion/conclusion.html

HTML+= index.html
SRC-index.html=../modules/index.html


.PHONY: print
print: ${DOCUMENTS}


.PHONY: clean distclean
clean:
	${RM} ${DOCUMENTS} ${HTML}

define target_rules
all: $(1)

$(1): ${SRC-$(1)}
	ln -sf $$^ $$@

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
