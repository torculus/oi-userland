#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Alexander Pyhalov
# Copyright 2018 Michal Nowak
# Copyright 2022 Andreas Wacknitz
#
BUILD_STYLE= justmake
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= 	pgbadger
COMPONENT_VERSION= 	12.4
COMPONENT_SUMMARY= 	A fast PostgreSQL log analyzer
COMPONENT_SRC= 		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= 	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= sha256:25456f0ea76e1de946d2bf09d937e9e830ca953ae4544a72bb9b747f11b4711a
COMPONENT_ARCHIVE_URL=	https://github.com/darold/pgbadger/archive/refs/tags/v$(COMPONENT_VERSION).tar.gz
COMPONENT_PROJECT_URL=	https://dalibo.github.io/pgbadger/
COMPONENT_FMRI=	database/postgres/$(COMPONENT_NAME)
COMPONENT_CLASSIFICATION=	System/Databases
COMPONENT_LICENSE=	PostgreSQL
COMPONENT_LICENSE_FILE=	LICENSE

TEST_TARGET= $(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

# Using makemaker.mk here is an overkill,
# because we don't need versioned pgbadger
COMPONENT_PRE_BUILD_ACTION = ( cd $(BUILD_DIR_64) && $(PERL) Makefile.PL )

PKG_PROTO_DIRS += $(BUILD_DIR_64)

# Auto-generated dependencies
PERL_REQUIRED_PACKAGES += runtime/perl
