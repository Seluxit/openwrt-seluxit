# 
# Copyright (C) 2006 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
#
# Copyright (C) 2017 Seluxit ApS 
#
# This is free software, licensed under the GNU General Public License v2.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=roundtest
PKG_VERSION:=0.0.1
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/sigidagi/round.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION:=3e1f247a5c2df4f6ae06fce268bf2f9ec14495bc
PKG_MAINTAINER:=Sigitas Dagilis<sigis@seluxit.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/roundtest
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Round test....
endef

define Package/roundtest/description
	Just a simple test. 
endef

define Package/roundtest/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/roundtest $(1)/usr/bin/
endef

$(eval $(call BuildPackage,roundtest))

