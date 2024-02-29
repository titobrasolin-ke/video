#
# Copyright (C) 2020 OpenWrt
# Author: Mirko Vogt <mirko-openwrt@nanl.de>
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=qt5serialbus
PKG_VERSION:=5.15.12
PKG_RELEASE:=1
PKG_HASH:=6104dbb447ec475337ca96a07bf26d4fb3d06a6ff710a00892a16952a76aebf1

PKG_SYS_NAME:=qtserialbus-everywhere-src-$(PKG_VERSION)
PKG_SOURCE:=qtserialbus-everywhere-opensource-src-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://download.qt.io/archive/qt/$(basename $(PKG_VERSION))/$(PKG_VERSION)/submodules

PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_SYS_NAME)
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5tools/host

include $(INCLUDE_DIR)/package.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

define Package/qt5serialbus
  SECTION:=video-frameworks
  CATEGORY:=Video
  SUBMENU:=Frameworks and Toolkits
  TITLE:=qt5serialbus
  URL:=http://qt.io
  MAINTAINER:=Yaroslav Petrov <info@lank.me>
  DEPENDS:=+qt5serialport
endef

define Package/qt5serialbus/install
	$(call Build/Install/Serialbus,$(1),*)
endef

$(eval $(call BuildPackage,qt5serialbus))
