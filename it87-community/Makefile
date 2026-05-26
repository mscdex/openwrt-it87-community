include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=it87-community
PKG_RELEASE:=1

PKG_SOURCE_URL:=https://github.com/frankcrawford/it87
PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2026-04-16
PKG_SOURCE_VERSION:=20f2f2f4c92c14fcdd26f60d050e693ad2c30bf8
PKG_MIRROR_HASH:=skip
PKG_HASH:=skip

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk

define KernelPackage/hwmon-it87-community
  SUBMENU:=Hardware Monitoring Support
  TITLE:=Community IT87 Hardware Monitor Driver
  URL:=https://github.com/frankcrawford/it87.git
  FILES:=$(PKG_BUILD_DIR)/it87.ko
  AUTOLOAD:=$(call AutoProbe,it87)
  DEPENDS:=+kmod-hwmon-core @TARGET_x86_64
endef

define KernelPackage/hwmon-it87-community/description
  A community fork of the IT87 hardware monitoring driver supporting newer ITE Super I/O chips.
endef

define Build/Compile
	$(KERNEL_MAKE) \
		M="$(PKG_BUILD_DIR)" \
    EXTRA_CFLAGS="-Wno-error=unused-function" \
		modules
endef

$(eval $(call KernelPackage,hwmon-it87-community))
