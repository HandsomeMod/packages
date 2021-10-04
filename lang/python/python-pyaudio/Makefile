#
# Copyright (C) 2020-2021 HandsomeMod Project
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyaudio
PKG_VERSION:=0.2.11
PKG_RELEASE:=1

PYPI_NAME:=PyAudio
PKG_HASH:=93bfde30e0b64e63a46f2fd77e85c41fd51182a4a3413d9edfaf9ffaa26efb74

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-pyaudio
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Python Bindings for PortAudio.
  URL:=https://people.csail.mit.edu/hubert/pyaudio
  DEPENDS:= +python3-light +portaudio
endef

define Package/python3-pyaudio/description
Python Bindings for PortAudio.
endef

$(eval $(call Py3Package,python3-pyaudio))
$(eval $(call BuildPackage,python3-pyaudio))
$(eval $(call BuildPackage,python3-pyaudio-src))
