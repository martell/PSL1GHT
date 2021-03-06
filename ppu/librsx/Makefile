#---------------------------------------------------------------------------------
# Clear the implicit built in rules
#---------------------------------------------------------------------------------
.SUFFIXES:
#---------------------------------------------------------------------------------

ifeq ($(strip $(PSL1GHT)),)
$(error "Please set PSL1GHT in your environment. export PSL1GHT=<path>")
endif

include	$(PSL1GHT)/ppu_rules

BUILD		:=	build

#---------------------------------------------------------------------------------
ifeq ($(strip $(PLATFORM)),)
#---------------------------------------------------------------------------------
export BASEDIR		:= $(CURDIR)
export DEPS			:= $(BASEDIR)/deps
export LIBS			:=	$(BASEDIR)/lib

#---------------------------------------------------------------------------------
else
#---------------------------------------------------------------------------------

export LIBDIR		:= $(LIBS)/$(PLATFORM)
export DEPSDIR		:=	$(DEPS)/$(PLATFORM)

#---------------------------------------------------------------------------------
endif
#---------------------------------------------------------------------------------

LIBRARY		:= $(LIBDIR)/librsx

#---------------------------------------------------------------------------------
DEFINCS		:= -I$(BASEDIR) -I$(BASEDIR)/../include -I$(BASEDIR)/../include/rsx
INCLUDES	:=	$(DEFINCS)

CFLAGS		:= -O2 -mregnames -Wall -mcpu=cell $(MACHDEP) -DLIBRSX_INTERNAL $(INCLUDES) -Wa,-mcell
ASFLAGS		:=	$(MACHDEP) -mregnames -mcpu=cell -D__ASSEMBLY__ -Wa,-mcell $(INCLUDES)

#---------------------------------------------------------------------------------
VPATH :=	$(BASEDIR)

#---------------------------------------------------------------------------------
OBJS		:= \
			init.o buffer.o commands.o mm.o vertex_program.o fragment_program.o

all: ppu

#---------------------------------------------------------------------------------
ppu:
#---------------------------------------------------------------------------------
	@[ -d $(LIBS)/ppu ] || mkdir -p $(LIBS)/ppu
	@[ -d $(DEPS)/ppu ] || mkdir -p $(DEPS)/ppu
	@[ -d ppu ] || mkdir -p ppu
	@$(MAKE) PLATFORM=ppu lib -C ppu -f $(CURDIR)/Makefile

#---------------------------------------------------------------------------------
install: all
#---------------------------------------------------------------------------------
	@[ -d $(DESTDIR)/$(PPUNAME)/lib ] || mkdir -p $(DESTDIR)/$(PPUNAME)/lib
	@cp -frv $(CURDIR)/lib/ppu/*.a $(DESTDIR)/$(PPUNAME)/lib

#---------------------------------------------------------------------------------
$(LIBRARY).a: $(OBJS)
#---------------------------------------------------------------------------------

.PHONY: lib ppu install

#---------------------------------------------------------------------------------
lib: $(LIBRARY).a
#---------------------------------------------------------------------------------

#---------------------------------------------------------------------------------
clean:
#---------------------------------------------------------------------------------
	@echo clean ...
	@rm -rf ppu
	@rm -rf $(DEPS)
	@rm -rf $(LIBS)

-include $(DEPSDIR)/*.d
