SOURCES = array.cpp base64.cpp bytestream.cpp config.cpp crypto.cpp \
	  dirw_unix.c geolocation.cpp getopt.c dload.cpp hash.cpp \
	  hashmapbase.cpp ice.c icmp.cpp icmp6.cpp iconv.cpp \
	  inet_pton.c inetaddr.cpp log.cpp lz4.c main.cpp md5.cpp message.cpp \
	  msgrecv.cpp msgwq.cpp net.cpp nxcp.cpp pa.cpp parisc_atomic.cpp \
     qsort.c queue.cpp rwlock.cpp scandir.c serial.cpp sha1.cpp sha2.cpp \
     solaris9_atomic.c streamcomp.cpp string.cpp \
	  stringlist.cpp strmap.cpp strmapbase.cpp strptime.c strset.cpp \
	  strtoll.c strtoull.c table.cpp threads.cpp timegm.c tools.cpp \
	  tp.cpp unicode.cpp uuid.cpp wcstoll.c wcstoull.c xml.cpp \
	  wcscasecmp.cpp wcsncasecmp.cpp

lib_LTLIBRARIES = libnetxms.la

if HPUX_HPPA
libnetxms_la_SOURCES = ldcw.s $(SOURCES)
else
libnetxms_la_SOURCES = $(SOURCES)
endif
libnetxms_la_CPPFLAGS=-I@top_srcdir@/include
if USE_INTERNAL_EXPAT
libnetxms_la_CPPFLAGS+=-I@top_srcdir@/src/libexpat/libexpat
endif
libnetxms_la_LDFLAGS = -version-info $(NETXMS_LIBRARY_VERSION)
libnetxms_la_LIBADD =
if USE_INTERNAL_EXPAT
libnetxms_la_LIBADD += ../libexpat/libexpat/libnxexpat.la
endif
if USE_INTERNAL_LIBTRE
libnetxms_la_LIBADD += ../libtre/libnxtre.la
endif
if USE_INTERNAL_ZLIB
libnetxms_la_CPPFLAGS += -I../zlib
libnetxms_la_LIBADD += ../zlib/libnxzlib.la
endif

EXTRA_DIST = \
	libnetxms.vcproj \
	libnetxms.h ice.h lz4.h md5.h sha1.h sha2.h strmap-internal.h \
	dir.c dirw.c \
	seh.cpp StackWalker.cpp StackWalker.h \
	ldcw.s
