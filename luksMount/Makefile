include $(TOPDIR)/rules.mk

PKG_NAME:=luksMount
PKG_VERSION:=0.1.0
PKG_RELEASE:=1

# PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
# PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/releases/download/$(PKG_VERSION)/
# PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
# PKG_HASH:=80136c2b247b4d8cdd34b70960622ba22126150a286e49f3e77cda5fcef36294
PKG_LICENSE:=GPL2
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=TPM2
  TITLE:=Luks Mount Utility
  URL:=https://girhub.com/armseb
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/description
  Luks partition mount utility using TPM2
endef

define Package/foo/install
	$(INSTALL_DIR) $(1)/etc
	$(CP) files/crypttab $(1)/etc/
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) files/passphrase-from-tpm $(1)/usr/bin/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
