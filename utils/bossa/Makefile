#
# Copyright (C) 2017-2018 Daniel Engberg <daniel.engberg.lists@pyret.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bossa
PKG_VERSION:=1.8
PKG_RELEASE:=1
PKG_MAINTAINER:=
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/shumatech/BOSSA.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_MIRROR_HASH:=8c315b399f9b2c3de02c7c9279ee0c67d80be0b0e5833581a55da49a951002de

include $(INCLUDE_DIR)/package.mk

define Package/bossa
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Flash programming utility for Atmel SAM
  URL:=https://github.com/shumatech/BOSSA
  DEPENDS:=+libstdcpp
endef

define Package/bossa/description
  flash programming utility for Atmel SAM
endef

define Build/Compile
	Q=$(TARGET_CROSS) $(MAKE) -C $(PKG_BUILD_DIR) strip-bossac
endef

define Package/bossa/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bossac $(1)/usr/bin/
endef

$(eval $(call BuildPackage,bossa))
