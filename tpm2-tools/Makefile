include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-tools
PKG_VERSION:=3.1.2
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/releases/download/$(PKG_VERSION)/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=80136c2b247b4d8cdd34b70960622ba22126150a286e49f3e77cda5fcef36294
PKG_FIXUP:=configure
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_DEPENDS:=tpm2-tss tpm2-abrmd libopenssl libcurl

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=TPM2
  TITLE:=TPM2-TOOLS
  URL:=https://github.com/tpm2-software/tpm2-tools
  DEPENDS+= +tpm2-tss +tpm2-abrmd +libopenssl +libcurl
endef

TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATIONS)

define Package/$(PKG_NAME)/description
  TPM (Trusted Platform Module) 2 tools
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_activatecredential $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_certify $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_create $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_createpolicy $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_createprimary $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_dictionarylockout $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_encryptdecrypt $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_evictcontrol $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_getcap $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_getmanufec $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_getpubak $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_getpubek $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_getrandom $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_hash $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_hmac $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_listpersistent $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_load $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_loadexternal $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_makecredential $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_nvdefine $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_nvlist $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_nvread $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_nvreadlock $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_nvrelease $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_nvwrite $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_pcrevent $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_pcrextend $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_pcrlist $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_quote $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_rc_decode $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_readpublic $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_rsadecrypt $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_rsaencrypt $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_send $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_sign $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_startup $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_takeownership $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_unseal $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2_verifysignature $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
