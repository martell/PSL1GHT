#---------------------------------------------------------------------------------
# Clear the implicit built in rules
#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

all:

install:
	@[ -d $(DESTDIR)/$(PPUNAME)/include/vectormath ] || mkdir -p $(DESTDIR)/$(PPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/c $(DESTDIR)/$(PPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/cpp $(DESTDIR)/$(PPUNAME)/include/vectormath

clean:

.PHONY: all clean install
