#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2016 EveryCity Ltd. All rights reserved.
# Copyright 2016 Adam Stevko. All rights reserved.
# Copyright 2022 Niklas Poslovski
# Copyright 2024 Goetz Fischer, R-A-C. All rights reserved.
#

BUILD_STYLE= justmake
USE_OPENSSL31= yes
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= haproxy
COMPONENT_FMRI= web/loadbalancer/haproxy
COMPONENT_VERSION_MJR= 2.8
COMPONENT_VERSION_MNR= 7
COMPONENT_VERSION= $(COMPONENT_VERSION_MJR).$(COMPONENT_VERSION_MNR)
COMPONENT_SUMMARY= A reliable, high performance TCP/HTTP load balancer
COMPONENT_PROJECT_URL= https://www.haproxy.org/
COMPONENT_SRC= $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= sha256:0d1a61161789c8ec50662955deffba50ab4ebe7efc6c0d947ff570ee7098e7f8
COMPONENT_ARCHIVE_URL= https://www.haproxy.org/download/$(COMPONENT_VERSION_MJR)/src/$(COMPONENT_ARCHIVE)
COMPONENT_CLASSIFICATION= System/Services
COMPONENT_LICENSE= HAPROXY

TEST_TARGET= $(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

LDFLAGS += -L$(OPENSSL_LIBDIR)

COMPONENT_PRE_BUILD_ACTION += $(CLONEY) $(SOURCE_DIR) $(@D)

COMPONENT_BUILD_ARGS +=	CC="$(CC)"
COMPONENT_BUILD_ARGS +=	LDFLAGS="$(LDFLAGS)"
COMPONENT_BUILD_ARGS +=	PREFIX="$(USRDIR)"
COMPONENT_BUILD_ARGS +=	SBINDIR="$(USRSBINDIR)"
COMPONENT_BUILD_ARGS +=	DOCDIR="$(USRDIR)/share/doc/haproxy"
COMPONENT_BUILD_ARGS +=	TARGET=solaris
COMPONENT_BUILD_ARGS +=	USE_OPENSSL=1
COMPONENT_BUILD_ARGS +=	USE_ZLIB=1
COMPONENT_BUILD_ARGS +=	USE_PCRE=1
COMPONENT_BUILD_ARGS +=	USE_REGPARM=1
COMPONENT_BUILD_ARGS +=	USE_PCRE_JIT=1
COMPONENT_BUILD_ARGS +=	PCRE_INC="$(USRINCDIR)/pcre"
COMPONENT_BUILD_ARGS +=	USE_LUA=1
COMPONENT_BUILD_ARGS +=	LUA_LIB_NAME=lua5.4
COMPONENT_BUILD_ARGS +=	LUA_INC="$(USRINCDIR)/lua5.4"
COMPONENT_BUILD_ARGS +=	ARCH=64
COMPONENT_BUILD_ARGS += SSL_INC="$(OPENSSL_INCDIR)"
COMPONENT_BUILD_ARGS +=	V=1

ifeq ($(strip $(MACH)),i386)
COMPONENT_BUILD_ARGS +=	CPU=x86_64
else
COMPONENT_BUILD_ARGS +=	CPU=ultrasparc
endif

COMPONENT_INSTALL_ARGS += $(COMPONENT_BUILD_ARGS)

COMPONENT_POST_INSTALL_ACTION += ( \
	cd $(@D) && \
	$(GMAKE) $(COMPONENT_BUILD_ARGS) admin/halog/halog && \
	$(CP) admin/halog/halog $(PROTOUSRSBINDIR) )

# Auto-generated dependencies
REQUIRED_PACKAGES += SUNWcs
REQUIRED_PACKAGES += library/pcre
REQUIRED_PACKAGES += library/security/openssl-31
REQUIRED_PACKAGES += library/zlib
REQUIRED_PACKAGES += runtime/lua-54
REQUIRED_PACKAGES += shell/ksh93
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/math
