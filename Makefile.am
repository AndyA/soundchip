DIST_SUBDIRS = m4 t

SUBDIRS = . t

ACLOCAL_AMFLAGS = -I m4

lib_LTLIBRARIES = libsoundchip.la

include_HEADERS = soundchip.h

bin_PROGRAMS = soundchip

libsoundchip_la_SOURCES = \
	soundchip.c soundchip.h

libsoundchip_la_CPPFLAGS = $(FFTW_CFLAGS) $(SNDFILE_CFLAGS) $(LIBPNG_CFLAGS)
libsoundchip_la_LDFLAGS = -avoid-version

soundchip_SOURCES = main.c
soundchip_CPPFLAGS = $(FFTW_CFLAGS) $(SNDFILE_CFLAGS) $(LIBPNG_CFLAGS)
soundchip_LDFLAGS = $(FFTW_LIBS) $(SNDFILE_LIBS) $(LIBPNG_LIBS)
soundchip_LDADD = libsoundchip.la

test: all
	cd t && $(MAKE) test
