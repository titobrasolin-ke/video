include $(TOPDIR)/rules.mk
 
PKG_NAME:=log4qt
PKG_VERSION:=1.5.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/MEONMedical/Log4Qt.git
PKG_SOURCE_DATE:=2020-02-14
PKG_SOURCE_VERSION:=v1.5.1
PKG_MIRROR_HASH:=868b2ff9b55459e72a48b46de9d70785489093c099a87249221e4fd597006a6b

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5tools/host
MAKE_PATH:=src

include $(INCLUDE_DIR)/package.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

QMAKE_TARGET+=QT+=sql
QMAKE_TARGET+=-after CONFIG-=hide_symbols
# https://github.com/MEONMedical/Log4Qt/blob/v1.5.1/src/log4qt/log4qt.pro#L7

define Package/log4qt
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Logging for the Qt cross-platform application framework
  URL:=https://github.com/MEONMedical/Log4Qt
  DEPENDS:=+libstdcpp +qt5base-concurrent +qt5base-core +qt5base-network \
    +qt5base-sql +qt5base-xml
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR_ROOT)/include/* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR_ROOT)/lib/* $(1)/usr/lib/
endef

define Package/log4qt/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR_ROOT)/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,log4qt))
