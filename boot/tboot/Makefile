include $(TOPDIR)/rules.mk

PKG_NAME:=tboot
PKG_VERSION:=1.9.7
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/tboot-$(PKG_VERSION)
PKG_SOURCE:=tboot-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/tboot
PKG_MD5SUM:=f0caf051adc8e53c7ad94533260649c0
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
