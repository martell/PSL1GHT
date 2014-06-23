
ifeq ($(strip $(PSL1GHT)),)
$(error "Please set PSL1GHT in your environment. export PSL1GHT=<path>")
endif

include	$(PSL1GHT)/spu_rules

#---------------------------------------------------------------------------------
# Clear the implicit built in rules
#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

all:
	@$(MAKE) -C libsputhread --no-print-directory

install-headers:
	@[ -d $(DESTDIR)/$(SPUNAME) ] || mkdir -p $(DESTDIR)/$(SPUNAME)
	@cp -frv include $(DESTDIR)/$(SPUNAME)

install: install-headers
	@$(MAKE) -C libsputhread install --no-print-directory

clean:
	@$(MAKE) -C libsputhread clean --no-print-directory

.PHONY: all clean install
