include $(TOPDIR)/rules.mk

PKG_NAME:=microperl
PKG_VERSION:=5.8.9
PKG_RELEASE:=1
PKG_REV:=4cce60ecd428bf8058e242fb9c38369ab75e350e

PKG_SOURCE:=perl-$(PKG_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=perl-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/perl-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)

include $(INCLUDE_DIR)/package.mk

define Package/microperl
	SUBMENU:=Perl
  	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Micro version of Perl
	URL:=https://www.cpan.org
	DEPENDS:=+libc
	#DEPENDS:=+libc +libpthread +libopenssl +libstdcpp
endef

define Build/Prepare
	$(Build/Prepare/Default)
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

MAKE_FLAGS = \
	CC="$(TARGET_CC)" \
	OPTIMIZE="-Os -w"

define Build/Compile
	$(call Build/Compile/Default, -f Makefile.micro regen_uconfig)
	$(call Build/Compile/Default, -f Makefile.micro)
endef

define Package/microperl/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/microperl $(1)/usr/bin/perl
endef

$(eval $(call BuildPackage,microperl))
