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

PKG_NAME:=qlora
PKG_VERSION:=0.0.2
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=hg
PKG_SOURCE_URL:=ssh://seluxit.com/../../revisioncontrol/hg/c/qlora
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=36d53df4a332
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Sigitas Dagilis<sigis@seluxit.com>


include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/qlora
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Qlora - gateway which talk IoT with Lora devices.
	DEPENDS:=+libcryptopp +libev +libuuid
endef

define Package/qlora/description
	Qlora is gateway software which communicates with LoRa meter device and Seluxit backend. 
endef

#define Build/Configure
	#cmake $(PKG_BUILD_DIR)/CMakeLists.txt
#endef

#define Build/Compile
	#$(MAKE) -C $(PKG_BUILD_DIR)
	#$(STRIP) $(PKG_BUILD_DIR)/src/qlora/qlora
#endef

define Package/qlora/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/qlora/qlora $(1)/usr/bin/
endef

$(eval $(call BuildPackage,qlora))

