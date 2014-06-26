#---------------------------------------------------------------------------------
# Clear the implicit built in rules
#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

all:

install:
	@[ -d $(DESTDIR)/$(SPUNAME)/include/vectormath ] || mkdir -p $(DESTDIR)/$(SPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/c $(DESTDIR)/$(SPUNAME)/include/vectormath
	@cp -frv $(CURDIR)/cpp $(DESTDIR)/$(SPUNAME)/include/vectormath

clean:

.PHONY: all clean install
