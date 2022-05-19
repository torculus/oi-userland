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
BUILD_STYLE=meson
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=picom
COMPONENT_VERSION=9.1
COMPONENT_SUMMARY=A lightweight compositor for X11
COMPONENT_PROJECT_URL=https://github.com/yshui/picom
COMPONENT_FMRI=desktop/picom
COMPONENT_CLASSIFICATION=Desktop/Window Managers
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_URL=https://github.com/yshui/picom/archive/refs/tags/v$(COMPONENT_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH=sha256:8700ac71bd496c91262c8576e29cb3aecf2b4ef48c04394a929509d3cb37b87d
COMPONENT_LICENSE=MIT
COMPONENT_LICENSE_FILE=picom.license
TEST_TARGET=$(NO_TESTS) # if no testsuite enabled
include $(WS_MAKE_RULES)/common.mk

COMPONENT_BUILD_ENVIRONMENT += LDFLAGS="-L/usr/local/lib"
COMPONENT_BUILD_ENVIRONMENT += CPPFLAGS="-I/usr/local/include -I/usr/include/uthash"
COMPONENT_BUILD_ACTION = LDFLAGS="-L/usr/include/uthash" CPPFLAGS="-I/usr/include/uthash" meson --buildtype=release . build

COMPONENT_INSTALL_ENVIRONMENT += meson configure -Dprefix=$(PROTO_DIR) build
COMPONENT_INSTALL_ACTION = LDFLAGS="-L/usr/include/uthash" CPPFLAGS="-I/usr/include/uthash" ninja -C build install

# Build dependencies
REQUIRED_PACKAGES+=developer/build/meson
REQUIRED_PACKAGES+=x11/library/libx11
REQUIRED_PACKAGES+=x11/library/libxext
REQUIRED_PACKAGES+=x11/library/xcb-util-xrm
REQUIRED_PACKAGES+=library/graphics/pixman
REQUIRED_PACKAGES+=system/library/libdbus
REQUIRED_PACKAGES+=library/libconfig
REQUIRED_PACKAGES+=library/libev
REQUIRED_PACKAGES+=library/uthash
