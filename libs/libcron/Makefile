# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=libcron
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/PerMalmberg/libcron.git
PKG_SOURCE_DATE:=2022-08-27
PKG_SOURCE_VERSION:=0dd9df49d7833a2d2119e4a6ff8282df58b12d5d
PKG_MIRROR_HASH:=bbcced5cd27f4e940bdb0d92b7014e31f8e00ca7928d0f642859669223448501

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>

PKG_BUILD_PARALLEL:=1
CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/libcron
  SECTION:=lib
  CATEGORY:=Libraries
  URL:=https://github.com/PerMalmberg/libcron
  TITLE:=A C++ scheduling library using cron formatting
  DEPENDS:=+libstdcpp
endef

define Package/libcron/description
  Libcron offers an easy to use API to add callbacks with corresponding
  cron-formatted strings.
endef

CMAKE_OPTIONS+= -DBUILD_SHARED_LIBS=ON

define Package/libcron/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/liblibcron.so $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libcron))
