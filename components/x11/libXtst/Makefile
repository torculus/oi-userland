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
# Copyright 2015 Aurelien Larcher
#

X11_CATEGORY=LIB
include ../../../make-rules/shared-macros.mk
include $(WS_MAKE_RULES)/x11.mk

COMPONENT_NAME=    libXtst
COMPONENT_VERSION= 1.2.4
COMPONENT_REVISION=1
COMPONENT_FMRI=    x11/library/libxtst
COMPONENT_SUMMARY= libXtst - Client library for X Record and Test extensions
COMPONENT_ARCHIVE_EXTENSION= .tar.xz
COMPONENT_ARCHIVE_HASH= sha256:84f5f30b9254b4ffee14b5b0940e2622153b0d3aed8286a3c5b7eeb340ca33c8

include $(WS_MAKE_RULES)/common.mk

COMPONENT_PREP_ACTION = ( cd $(@D) && PATH="$(PATH)" autoreconf -f -i )

CONFIGURE_OPTIONS+= --disable-static
CONFIGURE_OPTIONS+= --enable-shared
CONFIGURE_OPTIONS+= LIB_MAN_SUFFIX=3xtst

LD_OPTIONS += -M$(COMPONENT_DIR)/mapfile-vers

# Packages needed to generate documentation
REQUIRED_PACKAGES += library/libxslt
REQUIRED_PACKAGES += text/xmlto
REQUIRED_PACKAGES += x11/documentation/xorg-sgml-doctools

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += x11/library/libx11
REQUIRED_PACKAGES += x11/library/libxext
