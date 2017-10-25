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
PKG_VERSION:=0.0.1
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=hg
PKG_SOURCE_URL:=ssh://seluxit.com/../../revisioncontrol/hg/c/qlora
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION:=3319de611fa4

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/qlora
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Qlora - gateway which talk IoT with Lora devices.
	DEPENDS:=+libcryptopp +libev +liblua +libuuid
endef

define Package/qlora/description
	Qlora is gateway software which communicates with LoRa meter device and Seluxit backend. 
endef

#define Build/Prepare
	#mkdir -p $(PKG_BUILD_DIR)/src
	#$(CP) ./src/common $(PKG_BUILD_DIR)/src
	#$(CP) ./src/parser $(PKG_BUILD_DIR)/src
	#$(CP) ./src/qlora $(PKG_BUILD_DIR)/src
	#$(CP) ./CMakeLists.txt $(PKG_BUILD_DIR)
	#$(CP) -r ./cmake $(PKG_BUILD_DIR)

	#rm -f $(PKG_BUILD_DIR)/CMakeCache.txt
	#rm -fR $(PKG_BUILD_DIR)/CMakeFiles
	#rm -f $(PKG_BUILD_DIR)/Makefile
	#rm -f $(PKG_BUILD_DIR)/cmake_install.cmake
	#rm -f $(PKG_BUILD_DIR)/progress.make
#endef

#define Build/Configure
	#IN_OPENWRT=1 \
	#AR="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)ar" \
	#AS="$(TOOLCHAIN_DIR)/bin/$(TARGET_CC) -c $(TARGET_CFLAGS)" \
	#LD="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)ld" \
	#NM="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)nm" \
	#CC="$(TOOLCHAIN_DIR)/bin/$(TARGET_CC)" \
	#GCC="$(TOOLCHAIN_DIR)/bin/$(TARGET_CC)" \
	#CXX="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)g++" \
	#RANLIB="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)ranlib" \
	#STRIP="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)strip" \
	#OBJCOPY="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)objcopy" \
	#OBJDUMP="$(TOOLCHAIN_DIR)/bin/$(TARGET_CROSS)objdump" \
	#TARGET_CPPFLAGS="$(TARGET_CPPFLAGS)" \
	#TARGET_CFLAGS="$(TARGET_CFLAGS)" \
	#TARGET_LDFLAGS="$(TARGET_LDFLAGS)" \
	#cmake $(PKG_BUILD_DIR)/CMakeLists.txt
#endef

#define Build/Compile
	#$(MAKE) -C $(PKG_BUILD_DIR)
	#$(STRIP) $(PKG_BUILD_DIR)/qlora
#endef

define Package/qlora/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/qlora $(1)/usr/bin/
endef

$(eval $(call BuildPackage,qlora))

