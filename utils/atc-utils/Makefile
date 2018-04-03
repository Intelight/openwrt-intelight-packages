#
# Copyright (C) 2011-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=atc-utils
PKG_VERSION:=1.0.1
PKG_RELEASE:=0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:Intelight/atc-utils.git
PKG_SOURCE_VERSION:=master
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/atc-utils
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=ATC
  TITLE:=ATC Utility Programs
  DEPENDS:=+libpopt
endef

#define Build/Compile
#	$(call Build/Compile/Default, api)
#endef

define Build/Install
endef

define Package/atc-utils/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/libatc/libatc*so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/libbootid/libbootid*so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/utils/cpureset/cpureset $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/utils/eeprom/eeprom $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/utils/service/service $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/utils/ver/ver $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/utils/acfail $(1)/usr/bin/
	$(INSTALL_BIN) ./files/timesrc $(1)/usr/bin/
endef

$(eval $(call BuildPackage,atc-utils))

