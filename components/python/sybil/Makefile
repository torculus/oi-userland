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
# This file was automatically generated using the following command:
#   $WS_TOOLS/python-integrate-project sybil
#

BUILD_STYLE = setup.py

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME =		sybil
HUMAN_VERSION =			6.0.3
COMPONENT_REVISION =		1
COMPONENT_SUMMARY =		sybil - Automated testing for the examples in your code and documentation.
COMPONENT_PROJECT_URL =		https://github.com/simplistix/sybil
COMPONENT_ARCHIVE_URL =		\
	https://github.com/simplistix/sybil/archive/refs/tags/$(HUMAN_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH =	\
	sha256:435e528114acf5b6ff603b885aed428801b8b837e7f27f041f629decbed07e3e
COMPONENT_LICENSE =		MIT
COMPONENT_LICENSE_FILE =	LICENSE.txt

TEST_STYLE = pytest

#
# Following dependency loops were detected (where 'A --> B' means 'A needs B to
# run tests', and 'A ==> B' means 'A needs B for build and/or run'):
#
# sybil --> testfixtures ==> sybil
#
# To break loops we need to allow this project to integrate without testing in
# a case the required projects are not available yet (bootstrap).
#
PYTHON_TEST_BOOTSTRAP = yes

include $(WS_MAKE_RULES)/common.mk

# This project does not support tox so we need to provide test requirements
# manually.
TEST_REQUIREMENTS_EXTRAS += test

# https://github.com/pytest-dev/pluggy/issues/457
TEST_CONFLICTING_PACKAGES.python += library/python/faker
TEST_CONFLICTING_PACKAGES.python += library/python/pytest-checkdocs
TEST_CONFLICTING_PACKAGES.python += library/python/pytest-enabler
TEST_CONFLICTING_PACKAGES.python += library/python/pytest-randomly
TEST_CONFLICTING_PACKAGES.python += library/python/pytest-relaxed

# Auto-generated dependencies
PYTHON_REQUIRED_PACKAGES += runtime/python
TEST_REQUIRED_PACKAGES.python += library/python/mypy
TEST_REQUIRED_PACKAGES.python += library/python/pytest
TEST_REQUIRED_PACKAGES.python += library/python/pytest-cov
TEST_REQUIRED_PACKAGES.python += library/python/seedir
TEST_REQUIRED_PACKAGES.python += library/python/testfixtures
TEST_REQUIRED_PACKAGES.python += library/python/types-pyyaml
