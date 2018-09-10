include $(TOPDIR)/rules.mk

PKG_NAME:=cryptfs-tpm2
PKG_VERSION:=0.6.2
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/WindRiver-OpenSourceLabs/cryptfs-tpm2.git
# PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION:=1a1fe2bd67b5c4a3ec0ad5dd6dbb168df38144a4
PKG_SOURCE_DATE:=2018-02-16
# PKG_SOURCE_HASH:=88384df8b55c6d3be670fb9dccd67e29bda99162
PKG_FIXUP:=autoreconf
PKG_LICENSE:=BSD-2
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_DEPENDS:=tpm2-tss
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=CRYPTFS-TPM2
  URL:=http://trousers.sourceforge.net
  DEPENDS+= +libopenssl
endef

TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATION)

define Package/$(PKG_NAME)/description
CRYPTFS-TPM2
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
