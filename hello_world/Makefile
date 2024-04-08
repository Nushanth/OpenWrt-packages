include $(TOPDIR)/rules.mk

PKG_NAME:=hello-world
PKG_VERSION:=1.0.1
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/zilogic/hello_world_$(PKG_VERSION)
PKG_SOURCE:=$(TOPDIR)/zilogic/hello_world/src


PKG_MAINTAINER:=Nushanth.S <nushanthsaravanan@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/hello-world
  SECTION:=tryout
  CATEGORY:=Zilogic
  TITLE:=Hello-world 
endef

#MAINTAINER:=Nushanth.S <nushanthsaravanan@gmail.com>

define Package/world-world/description
 A simple Hello World! program.
endef

define Build/Prepare
		mkdir -p $(PKG_BUILD_DIR)
		cp $(PKG_SOURCE)/hello.c $(PKG_BUILD_DIR)
		patch $(PKG_BUILD_DIR)/hello.c patch/out.patch
		$(Build/Patch)
endef

define Build/Compile
		$(TARGET_CC) $(PKG_BUILD_DIR)/hello.c -o $(PKG_BUILD_DIR)/hello_world.o
endef

define Package/hello-world/install
	$(INSTALL_DIR) $(1)/usr/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hello_world.o $(1)/usr/
endef

$(eval $(call BuildPackage,hello-world))
