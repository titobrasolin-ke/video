#
# Copyright (C) 2020 OpenWrt
# Author: Mirko Vogt <mirko-openwrt@nanl.de>
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=qt5translations
PKG_VERSION:=5.15.12
PKG_RELEASE:=1
PKG_HASH:=a830ba6158ccb36fdae97ebfa33ac7c2c92f4b609786717830d65aa2e0e77612

PKG_SYS_NAME:=qttranslations-everywhere-src-$(PKG_VERSION)
PKG_SOURCE:=qttranslations-everywhere-opensource-src-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://download.qt.io/official_releases/qt/$(basename $(PKG_VERSION))/$(PKG_VERSION)/submodules

PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_SYS_NAME)
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5tools/host

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

define Package/qt5translations
  SECTION:=video-frameworks
  CATEGORY:=Video
  SUBMENU:=Frameworks and Toolkits
  TITLE:=qt5translations
  URL:=http://qt.io
  MAINTAINER:=Mirko Vogt <mirko-openwrt@nanl.de>
endef

define Package/qt5translations/install
	$(call Build/Install/Translations,$(1),*)
endef

$(eval $(call BuildPackage,qt5translations))
