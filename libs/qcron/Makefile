include $(TOPDIR)/rules.mk

PKG_NAME:=qcron
PKG_SOURCE_DATE:=2023-01-22
PKG_SOURCE_VERSION:=545c0daaaacdf40b9db023dc04a50131e5ede4aa
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/mankalas/qcron.git
PKG_MIRROR_HASH:=509926143d97f79d329693e9ec578a030c248591accfc3b8a238f5baa66cef0f

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_OPTIONS+=-DCMAKE_PREFIX_PATH=$(STAGING_DIR)/usr

define Package/qcron
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=A cron-like scheduler based on Qt
  URL:=https://github.com/mankalas/qcron
  DEPENDS:=+qt5base-core qt5base-test +libstdcpp
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/$(PKG_BUILD_DIR)/lib/libqcron.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/include $(1)/usr/include/qcron
	$(CP) $(PKG_BUILD_DIR)/src/*.hpp $(1)/usr/include/qcron/
endef

define Package/qcron/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/$(PKG_BUILD_DIR)/lib/libqcron.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,qcron))
