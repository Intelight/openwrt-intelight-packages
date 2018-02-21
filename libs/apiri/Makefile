#
# Copyright (C) 2011-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=apiri
PKG_VERSION:=2.0.0
PKG_RELEASE:=0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Intelight/APIRI.git
PKG_SOURCE_VERSION:=69964ae
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libtod
  SECTION:=libs
  CATEGORY:=Libraries
  SUBMENU:=ATC
  TITLE:=APIRI tod library
endef

define Package/libfio
  SECTION:=libs
  CATEGORY:=Libraries
  SUBMENU:=ATC
  TITLE:=APIRI fio library
endef

define Package/libfpui
  SECTION:=libs
  CATEGORY:=Libraries
  SUBMENU:=ATC
  TITLE:=APIRI fpui library
  DEPENDS:=+libtod +libfio
endef


define Build/Compile
	$(call Build/Compile/Default, api)
endef

define Build/Install
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/{lib,include}
	$(CP) $(PKG_BUILD_DIR)/fio/src/fioapi/libfio* $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/fio/src/fioapi/*.h $(1)/usr/include/
	$(CP) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/libfpui/libfpui* $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/libfpui/*.h $(1)/usr/include/
	$(CP) $(PKG_BUILD_DIR)/tod/src/libtod* $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/tod/src/*.h $(1)/usr/include/
endef

define Package/libtod/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tod/src/libtod*so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tod/timesrc/timesrc $(1)/usr/bin/
endef

define Package/libfio/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fio/src/fioapi/libfio*so* $(1)/usr/lib/
endef

define Package/libfpui/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/default
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/libfpui/libfpui*so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/FrontPanelManager/FrontPanelManager $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/MasterSelection/MasterSelection $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/SystemConfiguration/SystemConfiguration $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/SystemUtilities/atc_sc $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/fpuiexec/fpuiexec $(1)/usr/bin/
	$(CP) $(PKG_BUILD_DIR)/fpu/FrontPanelSystem/SystemConfiguration/ATCConfigurationMenu.txt $(1)/etc/default/ATCConfigurationMenu.txt
	ln -sf atc_sc $(1)/usr/bin/atc_sc_0
	ln -sf atc_sc $(1)/usr/bin/atc_sc_1
	ln -sf atc_sc $(1)/usr/bin/atc_sc_2
	ln -sf atc_sc $(1)/usr/bin/atc_sc_3
	ln -sf atc_sc $(1)/usr/bin/atc_sc_4
	ln -sf atc_sc $(1)/usr/bin/atc_sc_5
	ln -sf atc_sc $(1)/usr/bin/atc_sc_6
	ln -sf atc_sc $(1)/usr/bin/atc_sc_7
endef

$(eval $(call BuildPackage,libtod))
$(eval $(call BuildPackage,libfio))
$(eval $(call BuildPackage,libfpui))

