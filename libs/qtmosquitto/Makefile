include $(TOPDIR)/rules.mk

PKG_NAME:=qtmosquitto
PKG_SOURCE_DATE:=2023-04-11
PKG_SOURCE_VERSION:=a6ce795201b442e65b4d86179607e2244a85c0ad
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/marcopellin/qtmosquitto.git
PKG_MIRROR_HASH:=3742387d61c9f5d063408707e793e6db429b2f054f3775b728e4970e59ebb3b2

PKG_BUILD_DEPENDS:=qt5base

include $(INCLUDE_DIR)/package.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

QMAKE_TARGET+=-after INCLUDEPATH-=/usr/include
# https://github.com/marcopellin/qtmosquitto/blob/a6ce795201b442e65b4d86179607e2244a85c0ad/QtMosquitto.pro#L25

define Package/qtmosquitto
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Wrapper of the Mosquitto library for Qt 5
  URL:=https://github.com/marcopellin/qtmosquitto
  DEPENDS:=+libmosquitto-ssl +libstdcpp +qt5base-core +qt5base-network
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/qtmosquitto
	$(CP) $(PKG_BUILD_DIR)/source/*.hpp $(1)/usr/include/qtmosquitto/

	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/build/lib/* $(1)/usr/lib/
endef

define Package/qtmosquitto/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/build/lib/libqtmosquitto.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,qtmosquitto))
