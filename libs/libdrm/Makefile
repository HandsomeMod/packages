#
# Copyright (C) 2007-2016 OpenWrt.org
# Copyright (C) 2020-2021 HandsomeMod Project
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=libdrm
PKG_VERSION:=2.4.102
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://dri.freedesktop.org/libdrm
PKG_HASH:=8bcbf9336c28e393d76c1f16d7e79e394a7fce8a2e929d52d3ad7ad8525ba05b

PKG_MAINTAINER:=Lucian Cristian <lucian.cristian@gmail.com>
PKG_LICENSE:=BSD-3-Clause

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1
PKG_BUILD_DEPENDS:=meson/host

include $(INCLUDE_DIR)/package.mk
include ../../devel/meson/meson.mk

define Package/libdrm
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=+libpciaccess
  TITLE:=libdrm
  URL:=https://dri.freedesktop.org/
endef

define Package/libdrm/description
  LIBDRM is the cross-driver middleware which allows user-space applications
  (such as Mesa and 2D drivers) to communicate with the Kernel by the means
  of the DRI protocol.
endef

MESON_ARGS += \
	-Dlibkms=false \
	-Detnaviv=false \
	-Dcairo-tests=false \
	-Dman-pages=false \
	-Dvalgrind=false \
	-Dinstall-test-programs=false \
	-Dudev=false


ifeq ($(ARCH),arm)
    MESON_ARGS += \
    	-Dintel=false \
 	-Dradeon=false \
	-Damdgpu=false \
	-Dnouveau=false \
	-Dvmwgfx=false \
	-Domap=true \
	-Dfreedreno-kgsl=true \
	-Dexynos=true \
	-Dfreedreno=true \
	-Dtegra=true \
	-Dvc4=true  	
else ifeq ($(ARCH),aarch64)
    MESON_ARGS += \
    	-Dintel=false \
 	-Dradeon=false \
	-Damdgpu=false \
	-Dnouveau=false \
	-Dvmwgfx=false \
	-Domap=true \
	-Dfreedreno-kgsl=true \
	-Dexynos=true \
	-Dfreedreno=true \
	-Dtegra=true \
	-Dvc4=true
else ifeq ($(ARCH),i386)
    MESON_ARGS += \
    	-Dintel=true \
 	-Dradeon=true \
	-Damdgpu=true \
	-Dnouveau=true \
	-Dvmwgfx=true \
	-Domap=false \
	-Dfreedreno-kgsl=false \
	-Dexynos=false \
	-Dfreedreno=false \
	-Dtegra=false \
	-Dvc4=false	 
else ifeq ($(ARCH),x86_64)
    MESON_ARGS += \
    	-Dintel=true \
 	-Dradeon=true \
	-Damdgpu=true \
	-Dnouveau=true \
	-Dvmwgfx=true \
	-Domap=false \
	-Dfreedreno-kgsl=false \
	-Dexynos=false \
	-Dfreedreno=false \
	-Dtegra=false \
	-Dvc4=false
else
    MESON_ARGS += \
    	-Dintel=false \
 	-Dradeon=false \
	-Damdgpu=false \
	-Dnouveau=false \
	-Dvmwgfx=false \
	-Domap=false \
	-Dfreedreno-kgsl=false \
	-Dexynos=false \
	-Dfreedreno=false \
	-Dtegra=false \
	-Dvc4=false
endif

define Build/InstallDev
	$(INSTALL_DIR) \
	  $(1)/usr/include \
	  $(1)/usr/lib

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/include/* \
	  $(1)/usr/include/

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/{pkgconfig,*.so*} \
	  $(1)/usr/lib/
endef

define Package/libdrm/install
	$(INSTALL_DIR) \
	  $(1)/usr/lib

	$(CP) \
	  $(PKG_INSTALL_DIR)/usr/lib/*.so* \
	  $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libdrm))
