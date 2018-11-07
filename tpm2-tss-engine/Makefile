include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-tss-engine
PKG_VERSION:=2.0
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/tpm2-software/tpm2-tss-engine.git
# PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION:=2cc72e5fb58a14bc284f1e90df6a44aafc75d8ab
PKG_SOURCE_DATE:=2018-10-18
# PKG_SOURCE_HASH:=88384df8b55c6d3be670fb9dccd67e29bda99162
PKG_FIXUP:=autoreconf
PKG_LICENSE:=BSD-2
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_DEPENDS:=openssl libtool m4 ruby


PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=TPM2
  TITLE:=TPM2-TSS-ENGINE
  URL:=http://trousers.sourceforge.net
  DEPENDS+= +libopenssl
endef

#TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATION)

define Package/$(PKG_NAME)/description
TPM2-TSS-ENGINE
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
