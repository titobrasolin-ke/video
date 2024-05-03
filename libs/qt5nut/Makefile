include $(TOPDIR)/rules.mk

PKG_NAME:=qt5nut
PKG_VERSION:=0.6-beta-2
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/HamedMasafi/Nut.git
PKG_SOURCE_DATE:=2020-08-09
PKG_SOURCE_VERSION:=v0.6-beta-2
PKG_MIRROR_HASH:=f30a1d7e221678d723f2c21d68b7122d82925dc1c48272479386d012a2fb7a44

PKG_LICENSE:=LGPL-3.0
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5tools/host
MAKE_PATH:=src/nut

include $(INCLUDE_DIR)/package.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

QMAKE_TARGET+=-after QT-=gui

SYNCQT_TARGET=$(STAGING_DIR)/host/bin/syncqt.pl

define Build/Configure
	$(SYNCQT_TARGET) -v -version 0.6.0 -inc $(PKG_BUILD_DIR) $(PKG_BUILD_DIR)/sync.profile
	$(call Build/Configure/Default,)
endef

define Package/qt5nut
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Advanced, Powerful and easy to use ORM for Qt
  URL:=https://github.com/HamedMasafi/Nut
  DEPENDS:=+libstdcpp +qt5base-core +qt5base-sql
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

define Package/qt5nut/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,qt5nut))
