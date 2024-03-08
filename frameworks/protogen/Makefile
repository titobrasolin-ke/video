include $(TOPDIR)/rules.mk
 
PKG_NAME:=ProtoGen
PKG_VERSION:=v.3.5.d
PKG_RELEASE:=0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/billvaglienti/ProtoGen.git
PKG_SOURCE_DATE:=2023-09-29
PKG_SOURCE_VERSION:=v.3.5.d
PKG_MIRROR_HASH:=9cff7c9dcc53f85ea435751a0547f326d68a3524b4a9b7c6f84af2de8f0009b7

PKG_HOST_ONLY:=1
PKG_BUILD_PARALLEL:=1
HOST_BUILD_PARALLEL:=1
PKG_INSTALL:=1
HOST_BUILD_DEPENDS:=qt5base/host

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/nls.mk
-include $(STAGING_DIR)/host/mk/qmake.mk

define Package/ProtoGen
  SECTION:=video-frameworks
  CATEGORY:=Video
  SUBMENU:=Frameworks and Toolkits
  TITLE:=ProtoGen
  URL:=https://github.com/billvaglienti/ProtoGen
  DEPENDS:=+qt5base-core
  BUILDONLY:=1
endef

$(eval $(call BuildPackage,ProtoGen))
$(eval $(call HostBuild))
