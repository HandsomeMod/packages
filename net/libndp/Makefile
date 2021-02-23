#
# Copyright (C) 2020-2021 HandsomeMod Project
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libndp
PKG_VERSION:=1.7
PKG_RELEASE:=1
PKG_LICENSE:=LGPL-2.1
PKG_CPE_ID:=cpe:/a:libndp:libndp

PKG_SOURCE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/jpirko/libndp/archive
PKG_HASH:=44be73630ee785ed9f571f9aaaeba0e1d375fa337fd841270034c813b5b0e6fd

PKG_BUILD_PARALLEL:=1
PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk


define Package/libndp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=NDP Library
  URL:=https://github.com/jpirko/libndp/
endef

define Package/libndp/description
    Library for Neighbor Discovery Protocol
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/libndp.pc $(1)/usr/lib/pkgconfig
	$(SED) 's,/usr/bin,/usr,g' $(1)/usr/lib/pkgconfig/libndp.pc
	$(SED) 's,/usr/include,$$$${prefix}/include,g' $(1)/usr/lib/pkgconfig/libndp.pc
	$(SED) 's,/usr/lib,$$$${exec_prefix}/lib,g' $(1)/usr/lib/pkgconfig/libndp.pc
	$(SED) 's,/usr/bin,/usr,g' $(1)/usr/lib/pkgconfig/libndp.pc
endef


define Package/libndp/install
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/ndp.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libndp.so.* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/ndptool $(1)/usr/bin/
endef


$(eval $(call BuildPackage,libndp))
