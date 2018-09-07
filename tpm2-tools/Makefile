include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-tools
PKG_VERSION:=3.1.2
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/releases/download/$(PKG_VERSION)/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=a53b25214375a10d87d0c0b0a702a3402c1f19e218196d4a2a44810516b260e5
PKG_FIXUP:=patch-libtool
PKG_LICENSE:=CPL-1.0
PKG_LICENSE_FILES:=LICENCE
PKG_BUILD_DEPENDS:=tpm2-tss



PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=TPM2-TSS
  URL:=http://trousers.sourceforge.net
  DEPENDS+= +tpm2-tss
endef

#TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATI$


define Package/$(PKG_NAME)/description
  TPM2-TSS

endef


define Package/$(PKG_NAME)/install
        $(INSTALL_DIR) $(1)/usr/bin
endef


$(eval $(call BuildPackage,$(PKG_NAME)))
