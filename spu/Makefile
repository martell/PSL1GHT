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
