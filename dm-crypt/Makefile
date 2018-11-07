define KernelPackage/dm-crypt
  SUBMENU:=$(BLOCK_MENU)
  TITLE:=dm-crypt support
  KCONFIG:= \
        CONFIG_BLK_DEV_DM \
        CONFIG_DM_CRYPT=y
  FILES:=$(LINUX_DIR)/drivers/md/dm-crypt.ko
  AUTOLOAD:=$(call AutoLoad,30,dm-crypt)
endef

define KernelPackage/dm-crypt/description
 Kernel module for loopback device support
endef

$(eval $(call KernelPackage,dm-crypt))
