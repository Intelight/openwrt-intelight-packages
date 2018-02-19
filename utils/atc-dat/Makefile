#
# Copyright (C) 2011-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=atc-dat
PKG_VERSION:=1.0.0
#PKG_VERSION:=1.0.5
PKG_RELEASE:=0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:Intelight/atc-dat.git
PKG_SOURCE_VERSION:=master
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/atc-dat
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=ATC
  TITLE:=ATC DAT utility
endef

#define Build/Compile
#	$(call Build/Compile/Default, api)
#endef

define Build/Install
endef

define Package/atc-dat/install
	$(INSTALL_DIR) $(1)/opt/dat
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dat.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dat_composite.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chkled.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chkdisp $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chkfio $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chkfs.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chkfs_dd.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chkkeypd $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/speedfio $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/firmwareInfo $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/sertest $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ethtest $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mctltest $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dktest.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/eepromtest.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/linesynctest.sh $(1)/opt/dat/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/rtctest.sh $(1)/opt/dat/
endef

$(eval $(call BuildPackage,atc-dat))

