include $(TOPDIR)/rules.mk

PKG_NAME:=qt5mqtt
PKG_VERSION:=5.15.13
PKG_RELEASE:=1
PKG_HASH:=90edf48d17ddc14a9fa58893f46e99822b028e1c9588ccc33ebd108f60389451

PKG_SYS_NAME:=qtmqtt-everywhere-src-$(PKG_VERSION)
PKG_SOURCE:=qtmqtt-everywhere-opensource-src-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://download.qt.io/archive/qt/$(basename $(PKG_VERSION))/$(PKG_VERSION)/submodules

PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_SYS_NAME)
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5tools/host

include $(INCLUDE_DIR)/package.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

define Package/qt5mqtt
  SECTION:=video-frameworks
  CATEGORY:=Video
  SUBMENU:=Frameworks and Toolkits
  TITLE:=qt5mqtt
  DEPENDS:=+qt5base-core +qt5base-network +libstdcpp +libudev
endef

define Build/InstallDev
	$(call Build/Install/HostFiles,$(1))
	$(call Build/Install/Headers,$(1))
	$(call Build/Install/Libs,$(1),*)
endef

define Package/qt5mqtt/install
	$(call Build/Install/Libs,$(1),libQt5Mqtt)
endef

$(eval $(call BuildPackage,qt5mqtt))
