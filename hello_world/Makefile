include $(TOPDIR)/rules.mk

PKG_NAME:=hello-world
PKG_VERSION:=1.0.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Nushanth/Source-code.git

PKG_MAINTAINER:=Nushanth.S <nushanthsaravanan@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/hello-world
  SECTION:=tryout
  CATEGORY:=Zilogic
  TITLE:=Hello-world 
endef

define Package/world-world/description
  A simple Hello World! program.
endef

define Build/Prepare
		$(Build/Prepare/Default)
endef

define Build/Compile
		$(MAKE) -C $(PKG_BUILD_DIR)/Source-code/ \
			CC="$(TARGET_CC)"
endef

define Package/hello-world/install
	$(INSTALL_DIR) $(1)/usr/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/Source-code/hello.o $(1)/usr/
endef

$(eval $(call BuildPackage,hello-world))
