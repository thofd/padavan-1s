THISDIR = $(shell pwd)
XRAY_URL_BASE = https://github.com/felix-fly/xray-openwrt/releases/latest/download/
XRAY_NAME = xray-linux-mipsle
XRAY_URL = $(XRAY_URL_BASE)/$(XRAY_NAME).tar.gz

all: download_xray file_extract

download_xray:
	( if [ ! -f $(XRAY_NAME).tar.gz ]; then \
	  echo "start download xray"; \
		wget --no-check-certificate -O $(XRAY_NAME).tar.gz $(XRAY_URL); \
	fi )

file_extract:
	(
	  ls -l; \
	  if [ ! -f xray ]; then \
	    echo "unzip xray"; \
      tar xf $(XRAY_NAME).tar.gz; \
      rm -rf xray; \
      mv xray_softfloat xray; \
	  fi \
	  ls -l;
	)

clean:
  rm -rf $(XRAY_NAME).tar.gz

romfs:
	$(ROMFSINST) -p +x $(THISDIR)/xray /usr/bin/v2ray
