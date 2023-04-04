openwrt-netem
=============

OpenWrt packages for easy WAN emulation.

### Compiling the packages require the followinfg steps:
1. Setup an OpenWrt buildroot, checkout the openwrt repo. Refer to https://openwrt.org/docs/guide-developer/toolchain/use-buildsystem
2. Copy these folders into the my_packages folder of the openwrt buildroot and update the feeds. 
```
  ./scripts/feeds update -a
  ./scripts/feeds install netem-control
  ./scripts/feeds install luci-app-netem
```
3. Run `make menuconfig` and ensure both netem-control in Network and luci-app-netem in Luci > Applications is enabled
4. Compile both packages individually
```
   make package/netem-control/{clean,compile}
   make package/luci-app-netem/{clean,compile}
```
5. Resulting .ipk files will be placed in <buildroot>/bin/packages/x86_64/my_packages/
