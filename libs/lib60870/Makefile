include $(TOPDIR)/rules.mk

PKG_NAME:=lib60870
PKG_VERSION:=2.3.2
PKG_RELEASE:=1

PKG_MAINTAINER:=Tito Brasolin <tito.brasolin@kerberos.energy>

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/mz-automation/$(PKG_NAME)/archive/refs/tags/v$(PKG_VERSION).tar.gz?
PKG_HASH:=c63f170dc2dd25f7ec85d873be522f23d46838a84b072c8afda4118dfd5fc94d

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

MAKE_PATH:=lib60870-C
MAKE_FLAGS += \
	INSTALL_PREFIX="$(PKG_INSTALL_DIR)/usr"

define Package/lib60870
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=Library for IEC 60870-5 based protocols
	URL:=https://www.mz-automation.de/iec60870-5-101-104-c-source-code-library/
	DEPENDS+=+librt
	TITLE=lib60870
endef

define Package/lib60870/description
	Library for IEC 60870-5 based protocols
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/lib60870
	$(CP) $(PKG_INSTALL_DIR)/usr/include/*.h $(1)/usr/include/lib60870/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.a* $(1)/usr/lib/
endef

define Package/lib60870/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.a* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,lib60870))
