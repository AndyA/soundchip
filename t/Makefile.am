TESTBIN = basic

noinst_PROGRAMS = wrap $(TESTBIN)

noinst_LTLIBRARIES = libtest-support.la

libtest_support_la_SOURCES = tap.c tap.h
libtest_support_la_LDFLAGS = -static

LDADD = libtest-support.la ../libaraneae.la
AM_CPPFLAGS = $(LIBEVENT_CFLAGS) $(LIBCARES_CFLAGS) $(LIBSSL_CFLAGS)
AM_LDFLAGS = $(LIBEVENT_LIBS) $(LIBCARES_LIBS) $(LIBSSL_LIBS)

wrap_LDADD =
wrap_LDFLAGS =
wrap_CFLAGS =

test: $(TESTBIN)
	prove -e ./wrap $(TESTBIN) $(TESTPERL)

valgrind: $(TESTBIN)
	prove -e 'valgrind -q' $(addprefix ./,$(TESTBIN))
