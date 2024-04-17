include $(TOPDIR)/rules.mk

PKG_NAME:=inja
PKG_VERSION:=3.4.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://codeload.github.com/pantor/inja/zip/v$(PKG_VERSION)?
PKG_HASH:=4ad04d380b8377874c7a097a662c1f67f40da5fb7d3abc3851544f59c3613a20

PKG_BUILD_DEPENDS:=nlohmannjson

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/meson.mk

MESON_ARGS+=-Dbuild_tests=false -Dbuild_benchmark=false

define Package/inja
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Inja is a template engine for modern C++
  URL:=https://pantor.github.io/inja/
  BUILDONLY:=1
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/inja
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/include/inja/*.hpp $(1)/usr/include/inja/
endef

$(eval $(call BuildPackage,inja))
