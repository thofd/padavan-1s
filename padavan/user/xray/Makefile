THISDIR = $(shell pwd)
XRAY_URL_BASE = https://github.com/felix-fly/xray-openwrt/releases/latest/download/
XRAY_NAME = xray-linux-mipsle
XRAY_URL = $(XRAY_URL_BASE)/$(XRAY_NAME).tar.gz

all:download_xray file_extract

download_xray:
	( if [ ! -f $(XRAY_NAME).tar.gz ]; then \
		wget -t5 --timeout=20 --no-check-certificate -O $(XRAY_NAME).tar.gz $(XRAY_URL); \
	fi )

file_extract:
	( if [ ! -d $(XRAY_NAME) ]; then \
		tar xf $(XRAY_NAME).tar.gz; \
		rm xray; \
		mv xray_softfloat xray; \
	fi )

clean:
  rm -rf $(XRAY_NAME).tar.gz

romfs:
	$(ROMFSINST) -p +x $(THISDIR)/xray /usr/bin/v2ray
