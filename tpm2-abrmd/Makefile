include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-abrmd
PKG_VERSION:=2.0.3
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/releases/download/$(PKG_VERSION)/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=ff0ed283b0300cd784d6bf2b042e167020f8443602974e53b924e9fd98a4b515
#PKG_FIXUP:=autoreconf
PKG_LICENSE:=BSD-2-Clause
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_DEPENDS:=tpm2-tss dbus glib2
PKG_INSTALL:=1

TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATIONS)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=TPM2
  TITLE:=TPM2-ABRMD
  URL:=https://github.com/tpm2-software/tpm2-abrmd
  DEPENDS+= +tpm2-tss +libdbus +glib2
endef

define Package/$(PKG_NAME)/description
  TPM2 Access Broker & Resource Management Daemon implementing the TCG spec
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/.libs/libtss2-tcti-tabrmd.so* $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/tpm2-abrmd $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/usr/share/dbus-1/system.d
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dist/tpm2-abrmd.conf $(1)/usr/share/dbus-1/system.d
	$(INSTALL_DIR) $(1)/usr/share/dbus-1/system-services
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dist/com.intel.tss2.Tabrmd.service $(1)/usr/share/dbus-1/system-services
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/tss2
	$(CP) $(PKG_BUILD_DIR)/src/include/tss2-tcti-tabrmd.h $(1)/usr/include/tss2/

	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/.libs/libtss2-tcti-tabrmd.* $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/dist/tss2-tcti-tabrmd.pc $(1)/usr/lib/pkgconfig/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
