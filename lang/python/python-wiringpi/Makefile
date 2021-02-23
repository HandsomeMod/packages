#
# Copyright (C) 2020-2021 HandsomeMod Project
#
# This is free software, licensed under the GNU General Public License v2.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=py-wiringpi
PKG_VERSION:=2.60.0
PKG_RELEASE:=1
PKG_SOURCE:=wiringpi-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/w/wiringpi
PKG_HASH:=3ed8f12889956b7f624b20292f2ee90e0757196f89678b28d53864bb9c84884d
PKG_BUILD_DIR:=$(BUILD_DIR)/wiringpi-$(PKG_VERSION)

PKG_MAINTAINER:=HandsomeYingyan
PKG_LICENSE:=LGPL
PKG_LICENSE_FILES:=COPYING-LGPL


include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python-wiringpi/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python-wringpi
  URL:=https://libraries.io/pypi/wiringpi
  DEPENDS:=+wiringNP
endef

define Package/python-wiringpi/description
This package contains Python bindings for wiringpi2.
endef

define Package/python3-wiringpi
$(call Package/python-wiringpi/Default)
  DEPENDS+=+PACKAGE_python3-wiringpi:python3
  VARIANT:=python3
endef

define Package/python3-wiringpi/description
$(call Package/python-wiringpi/description)
.
(Variant for Python3)
endef

$(eval $(call Py3Package,python3-wiringpi))
$(eval $(call BuildPackage,python3-wiringpi))
$(eval $(call BuildPackage,python3-wiringpi-src))
