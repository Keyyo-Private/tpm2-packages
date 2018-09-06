include $(TOPDIR)/rules.mk

PKG_NAME:=tboot
PKG_VERSION:=1.9.7
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/tboot-$(PKG_VERSION)
PKG_SOURCE:=tboot-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/tboot
PKG_HASH:=7cfd83e37e3c010a92d6bbf0fe3697736c6cb7397395699642f50b2e3eb2ebab
PKG_CAT:=zcat

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk

define Package/tboot
  CATEGORY:=Base system
  SECTION:=boot
  TITLE:=Trusted Boot
  URL:=https://sourceforge.net/projects/tboot/
  DEPENDS:=@TARGET_x86||TARGET_x86_64
endef

$(eval $(call BuildPackage,tboot))
