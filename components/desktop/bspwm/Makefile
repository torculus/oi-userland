#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"). You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2022 Benjamin S. Osenbach
#
BUILD_BITS=64 # for binaries or 32_and_64 for libraries
BUILD_STYLE=justmake
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=bspwm
COMPONENT_VERSION=0.9.10
COMPONENT_SUMMARY=A tiling window manager based on binary space partitioning
COMPONENT_PROJECT_URL=https://github.com/baskerville/bspwm
COMPONENT_FMRI=desktop/window-manager/bspwm
COMPONENT_CLASSIFICATION=System/X11
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_URL=https://github.com/baskerville/bspwm/archive/refs/tags/$(COMPONENT_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH=sha256:0d0f5e465b9c27a5c2143c86189392fa297fad55253b9ed8f6854473d3928f8f
COMPONENT_LICENSE=BSD
TEST_TARGET=$(NO_TESTS) # if no testsuite enabled
include $(WS_MAKE_RULES)/common.mk

OMPONENT_BUILD_ENV += PREFIX=/usr

COMPONENT_INSTALL_ENV += PREFIX=/usr

# Auto-generated dependencies
