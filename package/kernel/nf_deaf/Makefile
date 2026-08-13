include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=nf_deaf
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0

include $(INCLUDE_DIR)/package.mk

define KernelPackage/nf-deaf
	SUBMENU:=Netfilter Extensions
	TITLE:=nf_deaf Netfilter postrouting hook
	FILES:=$(PKG_BUILD_DIR)/nf_deaf.ko
	KCONFIG:=
endef

define KernelPackage/nf-deaf/description
	Netfilter postrouting hook module for FTP related traffic manipulation
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Build/Compile
	+$(KERNEL_MAKE) M=$(PKG_BUILD_DIR) modules
endef

$(eval $(call KernelPackage,nf-deaf))
