include $(TOPDIR)/rules.mk

PKG_NAME:=pion
PKG_VERSION:=4.0.11

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:Intelight/pion-legacy.git
PKG_SOURCE_VERSION:=08aa242
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1
CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/pion
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=pion network library
  DEPENDS:=+boost
endef

$(eval $(call BuildPackage,pion))
