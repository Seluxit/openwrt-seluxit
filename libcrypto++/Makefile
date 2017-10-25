#
# Copyright (C) 2009-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
#PKG_REMOVE_FILES:=aclocal.m4 GNUmakefile
#PKG_SOURCE_URL:=http://ftp.de.debian.org/debian/pool/main/libc/libcrypto++/

include $(TOPDIR)/rules.mk

PKG_NAME:=libcryptopp
PKG_VERSION:=6.0.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/weidai11/cryptopp
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION:=5dcf3e8554a5216275e590114c74c45426b29160
PKG_MAINTAINER:=Sigitas Dagilis<sigis@seluxit.com>

#PKG_MD5SUM:=681f830145bf93cbc16113eaf61fbe2a

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libcryptopp
	SECTION:=libs
	CATEGORY:=Libraries
	DEPENDS:=+libpthread +libstdcpp
	TITLE:=Crypto++ is library for creating C++ programs which use cryptographic algorithms
	URL:=https://github.com/weidai11/cryptopp
endef

define Package/package/libcryptopp
	Crypto++ is library for creating C++ programs which use cryptographic algorithms.
	The library uses a Pipes & Filters architecture with heavy use of templates and
	abstract base classes.
endef

TARGET_LDFLAGS += \
	-lpthread

define Build/Compile
	$(MAKE) static dynamic -C $(PKG_BUILD_DIR) $(TARGET_CONFIGURE_OPTS) 
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/cryptopp
	$(CP) $(PKG_INSTALL_DIR)/usr/local/include/cryptopp/* $(1)/usr/include/cryptopp/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/libcryptopp.{a,so} $(1)/usr/lib/
endef

define Package/libcryptopp/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/libcryptopp.{a,so} $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libcryptopp))
