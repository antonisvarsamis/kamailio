# cdp Makefile

include ../../Makefile.defs
auto_gen=
NAME=cdp.so

DEFS+=-DKAMAILIO_MOD_INTERFACE

ifeq ($(CROSS_COMPILE),)
XML2CFG=$(shell which xml2-config)
endif

ifneq ($(XML2CFG),)
	DEFS += $(shell $(XML2CFG) --cflags )
	LIBS += $(shell $(XML2CFG) --libs)
else
	INCLUDES +=-I$(LOCALBASE)/include/libxml2 \
		-I$(LOCALBASE)/include
	LIBS += -L$(LOCALBASE)/lib -lxml2
endif

ifneq ($(OS),darwin)
	LIBS += -lrt
	LIBS += -lpthread
endif

include ../../Makefile.modules

