AUTOMAKE_OPTIONS = foreign
ACLOCAL_AMFLAGS = -I m4
SUBDIRS=external/libplist external/img4tool liboffsetfinder64 include

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = liboffsetfinder64.pc

ALL_LIBS=liboffsetfinder64/.libs/liboffsetfinder64.a
ALL_LIBS+=external/libplist/src/.libs/libplist.a
ALL_LIBS+=external/libplist/src/.libs/libplist++.a
ALL_LIBS+=external/img4tool/img4tool/.libs/libimg4tool.a

copy-all-libs: all
	-rm -r all_libs
	-mkdir all_libs
	-cp -f $(ALL_LIBS) all_libs
	-# glibtool wont work
	-libtool -static $(ALL_LIBS) -o all_libs/merged.a

