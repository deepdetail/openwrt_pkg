include $(TOPDIR)/rules.mk

PKG_NAME:=hello
PKG_VERSION:=1.0
PKG_RELEASE:=1
#PKG_REV:=4cce60ecd428bf8058e242fb9c38369ab75e350e

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
#PKG_SOURCE_PROTO:=git
#PKG_SOURCE_URL:=https://github.com/testing/hello.git

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)

include $(INCLUDE_DIR)/package.mk

define Package/hello
	SECTION:=utils
	TITLE:=Hello world program
	#URL:=https://github.com/testing/hello
	DEPENDS:=+libc
	#DEPENDS:=+libc +libpthread +libopenssl +libstdcpp
endef

#define Build/Prepare
#	#$(call Build/Prepare/Default)
#	mkdir -p $(PKG_BUILD_DIR)
#	$(CP) ./src/* $(PKG_BUILD_DIR)/
#endef

#MAKE_FLAGS = \
#    CC="$(TARGET_CC)" \
#    CXX="$(TARGET_CXX)"
#
#define Build/Compile
#	$(call Build/Compile/Default,-f Makefile.linux)
#endef

define Package/hello/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hello $(1)/usr/bin
endef

$(eval $(call BuildPackage,hello))
