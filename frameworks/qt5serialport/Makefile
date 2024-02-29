#
# Copyright (C) 2020 OpenWrt
# Author: Mirko Vogt <mirko-openwrt@nanl.de>
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=qt5serialport
PKG_VERSION:=5.15.12
PKG_RELEASE:=1
PKG_HASH:=0474d9ffc599491fef8ba28f222ffe5bba7f07be0591deb99ea819e991225914

PKG_SYS_NAME:=qtserialport-everywhere-src-$(PKG_VERSION)
PKG_SOURCE:=qtserialport-everywhere-opensource-src-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://download.qt.io/archive/qt/$(basename $(PKG_VERSION))/$(PKG_VERSION)/submodules

PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_SYS_NAME)
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5tools/host

include $(INCLUDE_DIR)/package.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

define Package/qt5serialport
  SECTION:=video-frameworks
  CATEGORY:=Video
  SUBMENU:=Frameworks and Toolkits
  TITLE:=qt5serialport
  URL:=http://qt.io
  MAINTAINER:=Yaroslav Petrov <info@lank.me>
endef

define Package/qt5serialport/install
	$(call Build/Install/Serialport,$(1),*)
endef

$(eval $(call BuildPackage,qt5serialport))
