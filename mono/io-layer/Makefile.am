
noinst_LTLIBRARIES = libwapi.la

AM_CPPFLAGS = \
	$(GLIB_CFLAGS)		\
	$(LIBGC_CPPFLAGS)	\
	-DMONO_BINDIR=\""$(bindir)"\"	\
	-I$(top_srcdir) \
	$(SHARED_CFLAGS)

libwapiincludedir = $(includedir)/mono-$(API_VER)/mono/io-layer

OTHER_H = \
	error.h		\
	io-layer.h	\
	wapi.h		\
	wapi-remap.h

OTHER_SRC = \
	error.c			\
	error.h			\
	io-layer.h		\
	wapi.h			\
	wapi.c


WINDOWS_H = \
	io-layer.h

WINDOWS_SRC = \
	io-layer.h		\
	io-layer-dummy.c

if HOST_WIN32
libwapi_la_SOURCES = $(WINDOWS_SRC) $(WINDOWS_H)
else
libwapi_la_SOURCES = $(OTHER_SRC) $(OTHER_H)
endif
if PLATFORM_DARWIN
libwapi_la_LIBADD = -lproc
endif

EXTRA_DIST =	\
	$(WINDOWS_SRC)
	$(OTHER_SRC)


