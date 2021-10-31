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
# Copyright 2021 Benjamin S. Osenbach
#
BUILD_BITS=64 # for binaries or 32_and_64 for libraries
BUILD_STYLE=meson
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=wayland
COMPONENT_VERSION=1.19.0
COMPONENT_SUMMARY=Core Wayland window system code and protocol
COMPONENT_PROJECT_URL=https://gitlab.freedesktop.org/wayland/wayland
COMPONENT_FMRI=wayland/wayland
COMPONENT_CLASSIFICATION=Desktop/Window Managers
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_URL=https://gitlab.freedesktop.org/wayland/wayland/-/archive/$(COMPONENT_VERSION)/$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=sha256:4e3b889468b9a4c2d16fc6489e28d000641e67c45dc97c4f6d9ecd3e261c895f
COMPONENT_LICENSE=MIT
COMPONENT_LICENSE_FILE=wayland.license
TEST_TARGET=$(NO_TESTS) # if no testsuite enabled
include $(WS_MAKE_RULES)/common.mk

# Build dependencies
REQUIRED_PACKAGES += library/libffi
