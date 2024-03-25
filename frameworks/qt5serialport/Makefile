#
# Copyright (C) 2020 OpenWrt
# Author: Mirko Vogt <mirko-openwrt@nanl.de>
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=qt5serialport
PKG_VERSION:=5.15.13
PKG_RELEASE:=1
PKG_HASH:=ebac963f00dafa75a3ec5643848d5abb4408ec5619643e22e420c1bc53d48ccc

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
  DEPENDS:=+qt5base-core +libstdcpp +libudev
endef

define Build/InstallDev
	$(call Build/Install/HostFiles,$(1))
	$(call Build/Install/Headers,$(1))
	$(call Build/Install/Libs,$(1),*)
endef

define Package/qt5serialport/install
	$(call Build/Install/Libs,$(1),libQt5SerialPort)
endef

$(eval $(call BuildPackage,qt5serialport))
