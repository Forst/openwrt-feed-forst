include $(TOPDIR)/rules.mk

PKG_NAME:=ndisc6
PKG_VERSION:=1.0.8
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://www.remlab.net/files/ndisc6
PKG_HASH:=1f2fb2dc1172770aa5a09d39738a44d8b753cc5e2e25e306ca78682f9fea0b4f

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/ndisc
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=IPv6 Discovery Tools (NDisc6)
  TITLE:=IPv6 Discovery Tools (NDisc6)
  URL:=https://www.remlab.net/ndisc6/
  DEPENDS:=@IPV6 +libpthread +librt
  MAINTAINER:=Foster Snowhill <gh@pen.gy>
endef

define Package/ndisc/description
NDisc6 is a small collection of useful tools for IPv6 networking.
endef


define Package/ndisc6
  $(call Package/ndisc)
  TITLE:=ICMPv6 Neighbor Discovery tool
endef

define Package/ndisc6/description
Performs IPv6 neighbor discovery in userland.
Replaces arping from the IPv4 world.
Can easily be used to monitor other hosts through scripts.
endef

define Package/ndisc6/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/ndisc6 $(1)/usr/bin/
endef

$(eval $(call BuildPackage,ndisc6))


define Package/rdisc6
  $(call Package/ndisc)
  TITLE:=ICMPv6 Router Discovery tool
endef

define Package/rdisc6/description
Queries IPv6 routers on the network for advertised prefixes.
Can be used to detect rogue IPv6 routers, monitor legitimate IPv6 routers.
Can also be used to force the local host into doing IPv6 autoconfiguration.
endef

define Package/rdisc6/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/rdisc6 $(1)/usr/bin/
endef

$(eval $(call BuildPackage,rdisc6))
