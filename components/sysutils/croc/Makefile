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

COMPONENT_NAME=croc
COMPONENT_VERSION=9.6.0
COMPONENT_SUMMARY=Easily and securely send things from one computer to another
COMPONENT_PROJECT_URL=https://github.com/schollz/croc
COMPONENT_FMRI=application/croc
COMPONENT_CLASSIFICATION=Applications/System Utilities
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_URL=https://github.com/schollz/croc/archive/refs/tags/v$(COMPONENT_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH=sha256:15fccb905872ae160c626ef7e47a92a8d78915b738d097865f177dfec925480b
COMPONENT_LICENSE=MIT
COMPONENT_LICENSE_FILE=croc.license
TEST_TARGET=$(NO_TESTS) # if no testsuite enabled
include $(WS_MAKE_RULES)/common.mk

COMPONENT_BUILD_ENV += GOOS="illumos"
COMPONENT_BUILD_ENV += GOPATH="$(SOURCE_DIR)/gopath"
COMPONENT_BUILD_ENV += PREFIX=/usr

COMPONENT_INSTALL_ENV += GOOS="illumos"
COMPONENT_INSTALL_ENV += GOPATH="$(SOURCE_DIR)/gopath"
COMPONENT_INSTALL_ENV += PREFIX=/usr

# Go doesn't like symbolic links, so copy the source directory
COMPONENT_COPY_ACTION=(cp -rL $(SOURCE_DIR)/* $(@D))

# Upstream Makefile doesn't create PROTO_DIR
COMPONENT_PRE_BUILD_ACTION=(install -d "$(PROTO_DIR)/usr/bin")

COMPONENT_BUILD_ACTION=cd $(@D) && go build
COMPONENT_INSTALL_ACTION=mv $(@D)/croc "$(PROTO_DIR)/usr/bin"

# Build dependencies
REQUIRED_PACKAGES+=developer/golang
# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
