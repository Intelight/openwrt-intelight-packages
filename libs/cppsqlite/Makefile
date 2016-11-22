include $(TOPDIR)/rules.mk

PKG_NAME:=cppsqlite
PKG_VERSION:=1.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:Intelight/cppsqlite.git
PKG_SOURCE_VERSION:=862e75b
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1
CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/cppsqlite
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=cppsqlite library
  DEPENDS:=+libsqlite3
endef

$(eval $(call BuildPackage,cppsqlite))
