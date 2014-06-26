#---------------------------------------------------------------------------------
# Clear the implicit built in rules
#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

ifeq ($(strip $(PSL1GHT)),)
$(error "Please set PSL1GHT in your environment. export PSL1GHT=<path>")
endif

include	$(PSL1GHT)/spu_rules

all:

install:
	@[ -d $(DESTDIR)/$(SPUNAME)/include/vectormath ] || mkdir -p $(DESTDIR)/$(SPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/c $(DESTDIR)/$(SPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/cpp $(DESTDIR)/$(SPUNAME)/include/vectormath

clean:

.PHONY: all clean install
