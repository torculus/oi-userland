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
#   $WS_TOOLS/python-integrate-project jaraco.test
#

BUILD_STYLE = pyproject

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME =		jaraco.test
HUMAN_VERSION =			5.4.0
COMPONENT_SUMMARY =		jaraco.test - Testing support by jaraco
COMPONENT_PROJECT_URL =		https://github.com/jaraco/jaraco.test
COMPONENT_ARCHIVE_HASH =	\
	sha256:dbd343878758adc54447d6115c461789adb31fc4073b212950243093ba317ec2
COMPONENT_LICENSE =		MIT
COMPONENT_LICENSE_FILE =	LICENSE

include $(WS_MAKE_RULES)/common.mk

# https://github.com/pytest-dev/pytest/issues/12112
PYTEST_ADDOPTS += --ignore jaraco/test/cpython.py

# Auto-generated dependencies
PYTHON_REQUIRED_PACKAGES += library/python/jaraco-collections
PYTHON_REQUIRED_PACKAGES += library/python/jaraco-context
PYTHON_REQUIRED_PACKAGES += library/python/jaraco-functools
PYTHON_REQUIRED_PACKAGES += library/python/setuptools
PYTHON_REQUIRED_PACKAGES += library/python/setuptools-scm
PYTHON_REQUIRED_PACKAGES += library/python/wheel
PYTHON_REQUIRED_PACKAGES += runtime/python
TEST_REQUIRED_PACKAGES.python += library/python/pytest
TEST_REQUIRED_PACKAGES.python += library/python/pytest-checkdocs
TEST_REQUIRED_PACKAGES.python += library/python/pytest-cov
TEST_REQUIRED_PACKAGES.python += library/python/pytest-enabler
TEST_REQUIRED_PACKAGES.python += library/python/pytest-mypy
