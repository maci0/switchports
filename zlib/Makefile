LIBTRANSISTOR_HOME=$(CURDIR)/../../libtransistor
include $(CURDIR)/../../libtransistor/libtransistor.mk

CC_FLAGS += -fuse-ld=lld 

$(CURDIR)/build/Makefile:
	echo $(CC_FLAGS)
	mkdir -p $(@D)
	cd $(@D); cmake -G "Unix Makefiles" $(CURDIR)/source/zlib \
		-DCMAKE_INSTALL_PREFIX=$(CURDIR)/../_output \
		-DCMAKE_C_COMPILER_WORKS=1 \
                -DCMAKE_C_COMPILER=$(CC) \
                -DCMAKE_C_FLAGS="$(CC_FLAGS)" \
                -DCMAKE_EXE_LINKER_FLAGS="-fuse-ld=lld" 
	cd $(CURDIR)/build; make zlib; cmake -DCMAKE_INSTALL_LOCAL_ONLY=1 -P cmake_install.cmake
 

clean:
	rm -Rf $(CURDIR)/build


