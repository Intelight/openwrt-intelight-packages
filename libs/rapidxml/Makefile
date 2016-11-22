include $(TOPDIR)/rules.mk

PKG_NAME:=rapidxml
PKG_VERSION:=1.13

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:Intelight/rapidxml.git
PKG_SOURCE_VERSION:=d74d360
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1
CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/rapidxml
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=rapidxml library
endef

$(eval $(call BuildPackage,rapidxml))
