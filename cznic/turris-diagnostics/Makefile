#
## Copyright (C) 2016 CZ.NIC z.s.p.o. (http://www.nic.cz/)
#
## This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
# #
#
include $(TOPDIR)/rules.mk

PKG_NAME:=turris-diagnostics
PKG_VERSION:=7
PKG_RELEASE:=2
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://gitlab.labs.nic.cz/turris/diagnostics.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_MAINTAINER:=Stepan Henek <stepan.henek@nic.cz>
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	TITLE:=$(PKG_NAME)
endef

define Package/$(PKG_NAME)/description
	Obtains diagnostics which are useful for troubleshooting of turris related functionality.
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/share/diagnostics/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/diagnostics.sh $(1)/usr/share/diagnostics/diagnostics.sh
	$(INSTALL_DIR) $(1)/usr/share/diagnostics/modules
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/modules/module.sh $(1)/usr/share/diagnostics/modules/module.sh
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/modules/*.module $(1)/usr/share/diagnostics/modules/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
