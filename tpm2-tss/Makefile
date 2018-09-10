include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-tss
PKG_VERSION:=2.0.1
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/releases/download/$(PKG_VERSION)/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=a53b25214375a10d87d0c0b0a702a3402c1f19e218196d4a2a44810516b260e5
PKG_FIXUP:=patch-libtool
PKG_LICENSE:=BSD-2
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_DEPENDS:=libgcrypt

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=TPM2-TSS
  URL:=http://trousers.sourceforge.net
  DEPENDS+= +libgcrypt
endef

TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATION)

define Package/$(PKG_NAME)/description
TPM2-TSS
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-mu/.libs/libtss2-mu.so* $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-sys/.libs/libtss2-sys.so* $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-esys/.libs/libtss2-esys.so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-tcti/.libs/libtss2-tcti-*.so* $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/include/tss2 $(1)/usr/include/

	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-mu/.libs/libtss2-mu.so* $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-sys/.libs/libtss2-sys.so* $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-esys/.libs/libtss2-esys.so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tss2-tcti/.libs/libtss2-tcti-*.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/lib/*.pc $(1)/usr/lib/pkgconfig/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
