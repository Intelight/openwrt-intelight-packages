include $(TOPDIR)/rules.mk

PKG_NAME:=snmp-pp
PKG_VERSION:=2.6

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:Intelight/snmp-pp.git
PKG_SOURCE_VERSION:=0b0f75e
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1
CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/snmp-pp
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=SNMP++ library
endef

#Force package to always be rebuilt
#define Package/libsnmp/install
#  rm -f $(PKG_BUILD_DIR)/.built
#endef

$(eval $(call BuildPackage,snmp-pp))
