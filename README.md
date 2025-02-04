# Forst's OpenWrt package feed

A collection of random packages that I find useful, and didn't find time to
submit upstream yet.


## How to add

Add the following to `feeds.conf`:

```
src-git forst https://github.com/Forst/openwrt-feed-forst.git
```

then fetch/update the feed and install all packages from it:

```console
$ ./scripts/feeds update forst
$ ./scripts/feeds install -a -p forst
```
