INCLUDE := -I${HOME}/eigen
CCFLAGS := -O3 -fPIC -march=native
UNAME_S := $(shell uname -s)
ifeq ($(UNAME_S), Linux)
	CCFLAGS += -shared
	LIB_NAME := libeigenmat.so
else
ifeq ($(UNAME_S), Darwin)
	CCFLAGS += -dynamiclib
	LIB_NAME := libeigenmat.dylib
else
	CCFLAGS +=  -shared
	LIB_NAME := libeigenmat.dll
endif
endif
all: eigenmat.cc eigenmat.h ziggurat.cc ziggurat.h
	g++ $(CCFLAGS) $(INCLUDE) -o $(LIB_NAME) eigenmat.cc ziggurat.cc

clean:
	rm -rf *.linkinfo *.pyc *.so
