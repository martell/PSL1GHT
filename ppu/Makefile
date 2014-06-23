

ifeq ($(strip $(PSL1GHT)),)
$(error "Please set PSL1GHT in your environment. export PSL1GHT=<path>")
endif

include	$(PSL1GHT)/ppu_rules

#---------------------------------------------------------------------------------
# Clear the implicit built in rules
#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

all:
	@$(MAKE) -C crt --no-print-directory
	@$(MAKE) -C sprx --no-print-directory
	@$(MAKE) -C librt --no-print-directory
	@$(MAKE) -C librsx --no-print-directory

install-headers:
	@[ -d $(DESTDIR)/$(PPUNAME) ] || mkdir -p $(DESTDIR)/$(PPUNAME)
	@cp -frv include $(DESTDIR)/$(PPUNAME)

install: install-headers
	@$(MAKE) -C crt install --no-print-directory
	@$(MAKE) -C sprx install --no-print-directory
	@$(MAKE) -C librt install --no-print-directory
	@$(MAKE) -C librsx install --no-print-directory

clean:
	@$(MAKE) -C crt clean --no-print-directory
	@$(MAKE) -C sprx clean --no-print-directory
	@$(MAKE) -C librt clean --no-print-directory
	@$(MAKE) -C librsx clean --no-print-directory

.PHONY: all clean install
