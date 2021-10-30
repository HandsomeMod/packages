#
# Copyright (C) 2020-2021 HandsomeMod Project
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=opencv-python
PKG_VERSION:=4.5.4.58
PKG_RELEASE:=1

PYPI_NAME:=opencv-python
PKG_HASH:=48288428f407bacba5f73d460feb4a1ecafe87db3d7cfc0730a49fb32f589bbf

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/opencv-python
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Pre-built CPU-only OpenCV packages for Python.
  URL:=https://github.com/opencv/opencv-python
  DEPENDS:= +python3-light +python3-numpy @BROKEN
endef

define Package/opencv-python/description
Pre-built CPU-only OpenCV packages for Python.
endef

$(eval $(call Py3Package,opencv-python))
$(eval $(call BuildPackage,opencv-python))
$(eval $(call BuildPackage,opencv-python-src))
