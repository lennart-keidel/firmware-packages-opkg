#
# Copyright (C) 2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lm4flash
PKG_VERSION:=0.1.3
PKG_RELEASE:=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/kostko/lm4tools.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=c37b42a7500a4f72f6614968dca0df6ae2ee7917
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

include $(INCLUDE_DIR)/package.mk

define Package/lm4flash
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=lm4flash
  DEPENDS:=+libusb-1.0
  MAKE_PATH:=lm4flash
endef

define Build/Prepare
	$(call Build/Prepare/Default)
	sed -i s/gcc/\$$$$\(CC\)/g $(PKG_BUILD_DIR)/lm4flash/Makefile
endef

define Package/lm4flash/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/lm4flash/lm4flash $(1)/usr/bin/lm4flash
endef

$(eval $(call BuildPackage,lm4flash))

