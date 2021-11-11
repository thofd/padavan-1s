THISDIR = $(shell pwd)
XRAY_URL_BASE := https://github.com/felix-fly/xray-openwrt/releases/latest/download/

XRAY_NAME := xray-linux-mipsle
XRAY_URL := $(XRAY_URL_BASE)/$(XRAY_NAME).tar.gz

all:
  wget $(XRAY_URL) -O $(XRAY_NAME).tar.gz; \
	tar xf $(XRAY_NAME).tar.gz; \
	rm xray; \
	mv xray_softfloat xray; \
	rm $(XRAY_NAME).tar.gz;

clean:
	echo "Clean xray done";

romfs:
