#---------------------------------------------------------------------------------
# Clear the implicit built in rules
#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

ifeq ($(strip $(PSL1GHT)),)
$(error "Please set PSL1GHT in your environment. export PSL1GHT=<path>")
endif

include	$(PSL1GHT)/ppu_rules

all:

install:
	@[ -d $(DESTDIR)/$(PPUNAME)/include/vectormath ] || mkdir -p $(DESTDIR)/$(PPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/c $(DESTDIR)/$(PPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/cpp $(DESTDIR)/$(PPUNAME)/include/vectormath

clean:

.PHONY: all clean install
