include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-abrmd
PKG_VERSION:=2.0.2_rc0
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/archive/
PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_HASH:=9a28ced7bed8a13fac1ea9fc6143091b4bcd6b7ac129b4e80ce344dcdcc7839a
PKG_FIXUP:=autoreconf
PKG_LICENSE:=CPL-1.0
PKG_LICENSE_FILES:=LICENCE

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=TPM2-TSS
  URL:=http://trousers.sourceforge.net
endef

define Package/$(PKG_NAME)/description
  TPM2-TSS

endef


$(eval $(call BuildPackage,$(PKG_NAME)))
