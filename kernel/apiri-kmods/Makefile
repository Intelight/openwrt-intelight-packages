#
# Copyright (C) 2011-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=apiri-kmods
PKG_VERSION:=2.0.0
PKG_RELEASE:=0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Intelight/APIRI.git
PKG_SOURCE_VERSION:=69964ae
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define KernelPackage/fiodriver
  SUBMENU:=APIRI Drivers
  TITLE:=APIRI fio kernel driver
  VERSION:=$(LINUX_VERSION)-$(PKG_VERSION)-$(PKG_RELEASE)
  FILES:=$(PKG_BUILD_DIR)/fio/src/fiodriver/fiodriver.ko
endef

define KernelPackage/front_panel
  SUBMENU:=APIRI Drivers
  TITLE:=APIRI fpui kernel driver
  VERSION:=$(LINUX_VERSION)-$(PKG_VERSION)-$(PKG_RELEASE)
  FILES:=$(PKG_BUILD_DIR)/fpu/FrontPanelSystem/FrontPanelDriver/front_panel.ko
endef

define KernelPackage/atc_tod
  SUBMENU:=APIRI Drivers
  TITLE:=APIRI tod kernel driver
  VERSION:=$(LINUX_VERSION)-$(PKG_VERSION)-$(PKG_RELEASE)
  FILES:=$(PKG_BUILD_DIR)/tod/atc_tod/atc_tod.ko
endef

MAKE_OPTS:= \
	ARCH="$(LINUX_KARCH)" \
	CROSS_COMPILE="$(TARGET_CROSS)" \

define Build/Compile
	$(MAKE) -C "$(LINUX_DIR)" \
		$(MAKE_OPTS) \
		M="$(PKG_BUILD_DIR)/fio/src/fiodriver" \
		modules

	$(MAKE) -C "$(LINUX_DIR)" \
		$(MAKE_OPTS) \
		M="$(PKG_BUILD_DIR)/fpu/FrontPanelSystem/FrontPanelDriver" \
		modules

	$(MAKE) -C "$(LINUX_DIR)" \
		$(MAKE_OPTS) \
		M="$(PKG_BUILD_DIR)/tod/atc_tod" \
		modules
endef

$(eval $(call KernelPackage,fiodriver))
$(eval $(call KernelPackage,front_panel))
$(eval $(call KernelPackage,atc_tod))

