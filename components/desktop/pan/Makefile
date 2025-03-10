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
# Copyright 2022 Niklas Poslovski
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=         pan
COMPONENT_VERSION=      0.157
COMPONENT_PROJECT_URL=  https://pan.rebelbase.com
COMPONENT_SUMMARY=      A powerful Newsgroup Article reader
COMPONENT_FMRI=         desktop/nntp/pan
COMPONENT_SRC=          $(COMPONENT_NAME)-v$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=      $(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH= sha256:1ab5f59a9e1e9cb9bfe978be55fda812d5b46936c1c14d9dae30a555c665eb51
COMPONENT_ARCHIVE_URL=	https://gitlab.gnome.org/GNOME/pan/-/archive/v$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_CLASSIFICATION= Applications/Internet
COMPONENT_LICENSE=      GPLv2
COMPONENT_LICENSE_FILE= COPYING

CONFIGURE_OPTIONS += --enable-gkr
CONFIGURE_OPTIONS += --with-gnutls

TEST_TARGET = $(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

COMPONENT_PREP_ACTION = ( cd $(@D) && PATH="$(PATH)" autoreconf --force --install )

LDFLAGS += -lsocket -lnsl

# SPARC needs math library
ifeq ($(strip $(MACH)),sparc)
REQUIRED_PACKAGES += system/library/math
endif

# Auto-generated dependencies
REQUIRED_PACKAGES += $(GCC_RUNTIME_PKG)
REQUIRED_PACKAGES += $(GXX_RUNTIME_PKG)
REQUIRED_PACKAGES += library/desktop/cairo
REQUIRED_PACKAGES += library/desktop/gdk-pixbuf
REQUIRED_PACKAGES += library/desktop/gtk3
REQUIRED_PACKAGES += library/desktop/gtkspell3
REQUIRED_PACKAGES += library/desktop/pango
REQUIRED_PACKAGES += library/glib2
REQUIRED_PACKAGES += library/gmime3
REQUIRED_PACKAGES += library/gnome/gcr
REQUIRED_PACKAGES += library/gnutls-3
REQUIRED_PACKAGES += library/libsecret
REQUIRED_PACKAGES += library/spell-checking/enchant
REQUIRED_PACKAGES += library/zlib
REQUIRED_PACKAGES += system/library
