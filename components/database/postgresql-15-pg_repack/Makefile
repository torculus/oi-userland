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
# Copyright 2023 Andreas Wacknitz
#

BUILD_BITS= 64
BUILD_STYLE= justmake
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=	pg_repack
COMPONENT_VERSION=	1.5.0
COMPONENT_SUMMARY=	pg_repack - utility to reorganize PostgreSQL tables on-line
COMPONENT_SRC=	$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).zip
COMPONENT_ARCHIVE_HASH= sha256:118542907ed6f1f713a45cc6b2daef8ca1e667f0c918bb9e24f390033fd52610
COMPONENT_ARCHIVE_URL=	https://api.pgxn.org/dist/pg_repack/$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL=	https://reorg.github.io/pg_repack/
COMPONENT_FMRI=	database/postgres-15/pg_repack
COMPONENT_CLASSIFICATION=	System/Databases
COMPONENT_LICENSE=	BSD
COMPONENT_LICENSE_FILE=	COPYRIGHT

PG_VERSION=	15

# Don't depend on host default pg_config
PATH= $(PG_HOME)/bin:/usr/sbin:/usr/bin

TEST_TARGET= $(NO_TESTS)

include $(WS_MAKE_RULES)/common.mk

# Manually added build dependencies
REQUIRED_PACKAGES += $(PG_DEVELOPER_PKG)

# Auto-generated dependencies
REQUIRED_PACKAGES += $(PG_LIBRARY_PKG)
REQUIRED_PACKAGES += database/postgres-15
REQUIRED_PACKAGES += system/library
