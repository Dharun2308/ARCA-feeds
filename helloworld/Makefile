include $(TOPDIR)/rules.mk

# Name, version and release number
# The name and version of your package are used to define the variable to point to the build directory of your package: $(PKG_BUILD_DIR)

PKG_NAME:=helloworld
PKG_VERSION:=1
PKG_RELEASE:=1
PKG_SOURCE_URL:=https://github.com/Dharun2308/ARCA-feeds.git
PKG_SOURCE_PROTO:=git
PKG_MAINTAINER:=Dharun

# Source settings (i.e. where to find the source codes)
# This is a custom variable, used below
# SOURCE_DIR:=/home/andrei/helloworld


include $(INCLUDE_DIR)/package.mk


# Package definition; instructs on how and where our package will appear in the overall configuration menu ('make menuconfig')
define Package/helloworld
	SECTION:=examples
	CATEGORY:=Examples
	TITLE:=Hello, world!
endef

# Package build instructions; invoke the target-specific compiler to first compile the source file, and then to link the file into the final executable
define Build/Compile
	$(TARGET_CC) $(TARGET_CFLAGS) -o $(PKG_BUILD_DIR)/helloworld.o -c $(PKG_BUILD_DIR)/helloworld.c
	$(TARGET_CC) $(TARGET_LDFLAGS) -o $(PKG_BUILD_DIR)/$1 $(PKG_BUILD_DIR)/helloworld.o
endef

# Package install instructions; create a directory inside the package to hold our executable, and then copy the executable we built previously into the folder
define Package/helloworld/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/helloworld $(1)/usr/bin
endef

# This command is always the last, it uses the definitions and variables we give above in order to get the job done

$(eval $(call BuildPackage,$(PKG_NAME)))
