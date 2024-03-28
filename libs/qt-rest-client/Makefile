include $(TOPDIR)/rules.mk

PKG_NAME:=qt-rest-client
PKG_SOURCE_DATE:=2015-01-03
PKG_SOURCE_VERSION:=51c465f0ddd193e4c26fe5a65024ef62d3725707
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/emilio-simoes/qt-rest-client.git
PKG_MIRROR_HASH:=5fa44f9bb49973b0460ee7ece7413b2926fe54e718d1ab49964d9a996c760df8

PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5base
MAKE_PATH:=rest-client

include $(INCLUDE_DIR)/package.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

# QMAKE_TARGET+=-after CONFIG-=staticlib
# https://github.com/emilio-simoes/qt-rest-client/blob/master/rest-client/rest-client.pro#L13

define Package/qt-rest-client
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=REST client implementation in QT 5.4.0 and C++11
  URL:=https://github.com/emilio-simoes/qt-rest-client
  BUILDONLY:=1
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/include/$(MAKE_PATH)
	$(INSTALL_DIR) $(1)/usr/include/$(MAKE_PATH)/auth
	$(INSTALL_DIR) $(1)/usr/include/$(MAKE_PATH)/utils
	$(CP) $(PKG_BUILD_DIR)/$(MAKE_PATH)/*.h $(1)/usr/include/$(MAKE_PATH)/
	$(CP) $(PKG_BUILD_DIR)/$(MAKE_PATH)/auth/*.h $(1)/usr/include/$(MAKE_PATH)/auth/
	$(CP) $(PKG_BUILD_DIR)/$(MAKE_PATH)/utils/*.h $(1)/usr/include/$(MAKE_PATH)/utils/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR_ROOT)/usr/lib/librest-client.a $(1)/usr/lib/
endef

$(eval $(call BuildPackage,qt-rest-client))
