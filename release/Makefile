PUB_FILES?=		${RELEASE_FILES}
PUB_SERVER?=	ver.miun.se
PUB_DIR?=		/srv/web/svn/courses/security/dasak
PUB_USER?=		
PUB_GROUP?=		svn
PUB_METHOD?=	ssh
PUB_VCS?=		git
PUB_AUTOTAG?=	true

.PHONY: release
release: ${RELEASE_FILES}

RELEASE_FILES+=	studyguide.pdf
SRC-studyguide.pdf=../studyguide/studyguide.pdf

RELEASE_FILES+=	foundations-slides.pdf
SRC-foundations-slides.pdf=../modules/foundations/overview/overview.pdf

RELEASE_FILES+=	usability-slides.pdf
SRC-usability-slides.pdf=../modules/usability/overview/overview.pdf

RELEASE_FILES+=	infotheory-slides.pdf
SRC-infotheory-slides.pdf=../modules/infotheory/basics/basics.pdf

RELEASE_FILES+=	crypto-slides.pdf
SRC-crypto-slides.pdf=../modules/appliedcrypto/overview/overview-slides.pdf

RELEASE_FILES+=	spuriouslab.pdf
SRC-spuriouslab.pdf=../modules/appliedcrypto/spuriouslab/spuriouslab.pdf

RELEASE_FILES+=	auth-slides.pdf
SRC-auth-slides.pdf=../modules/auth/overview/overview.pdf

RELEASE_FILES+=	pwdguess.pdf
SRC-pwdguess.pdf=../modules/auth/passwd/pwdguess/pwdguess.pdf

RELEASE_FILES+=	pwdpolicies.pdf
SRC-pwdpolicies.pdf=../modules/auth/passwd/pwdpolicies/pwdpolicies.pdf

RELEASE_FILES+=	fverif-slides.pdf
SRC-fverif-slides.pdf=../modules/fverif/intro/intro.pdf

RELEASE_FILES+=	ac-slides.pdf
SRC-ac-slides.pdf=../modules/ac/overview/overview.pdf

RELEASE_FILES+=	refmon-slides.pdf
SRC-refmon-slides.pdf=../modules/ac/refmon/refmon.pdf

RELEASE_FILES+=	accountability-slides.pdf
SRC-accountability-slides.pdf=../modules/accountability/overview/overview.pdf

RELEASE_FILES+=	pricomlab.pdf
SRC-pricomlab.pdf=../modules/pricomlab/pricomlab.pdf

RELEASE_FILES+=	toolslab.pdf
SRC-toolslab.pdf=../modules/toolslab/toolslab.pdf

RELEASE_FILES+=	trustcomp-slides.pdf
SRC-trustcomp-slides.pdf=../modules/trustcomp/overview/overview.pdf

RELEASE_FILES+=	drmlab.pdf
SRC-drmlab.pdf=../modules/trustcomp/drmlab/drm.pdf

RELEASE_FILES+=	sidechannels-slides.pdf
SRC-sidechannels-slides.pdf=../modules/sidechannels/overview/overview.pdf

RELEASE_FILES+=	software-slides.pdf
SRC-software-slides.pdf=../modules/software/overview/overview-slides.pdf

RELEASE_FILES+=	stacksmashlab.pdf
SRC-stacksmashlab.pdf=../modules/software/stacksmashlab/stacksmash.pdf

RELEASE_FILES+=	malwarelab.pdf
SRC-malwarelab.pdf=../modules/software/malwarelab/malware.pdf

RELEASE_FILES+=	ethics.pdf
SRC-ethics.pdf=../modules/ethics/profession/profession.pdf


.PHONY: print
print: ${RELEASE_FILES}


.PHONY: clean distclean

define target_rules
release: $(1)

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

$(foreach target,${RELEASE_FILES},$(eval $(call target_rules,${target})))


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/doc.mk
