include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-tss
PKG_VERSION:=2.0.1
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/releases/download/v$(PKG_VERSION)/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_MD5SUM:=85a978c4e03fefd4b73cbeadde7c4d0b
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
