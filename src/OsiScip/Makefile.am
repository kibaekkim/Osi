# Copyright (C) 2020 Kibaek Kim.
# All Rights Reserved.
# This file is distributed under the Eclipse Public License.


include $(top_srcdir)/BuildTools/Makemain.inc

########################################################################
#                             libOsiScip                                 
########################################################################

# Name of the library compiled in this directory.
lib_LTLIBRARIES = libOsiScip.la

# List all source files for this library, including headers
libOsiScip_la_SOURCES = OsiScipSolverInterface.cpp OsiScipSolverInterface.hpp

# List all additionally required libraries
libOsiScip_la_LIBADD = ../Osi/libOsi.la $(OSISCIPLIB_LFLAGS)

# This is for libtool (on Windows)
libOsiScip_la_LDFLAGS = $(LT_LDFLAGS)

# Here list all include flags, relative to this "srcdir" directory.
AM_CPPFLAGS = -I$(srcdir)/../Osi $(OSISCIPLIB_CFLAGS)

########################################################################
#                Headers that need to be installed                     #
########################################################################

# Here list all the header files that are required by a user of the library,
# and that therefore should be installed in 'include/coin-or'
includecoindir = $(pkgincludedir)
includecoin_HEADERS = OsiScipSolverInterface.hpp

install-exec-local:
	$(install_sh_DATA) config_osiscip.h $(DESTDIR)$(includecoindir)/OsiScipConfig.h

uninstall-local:
	rm -f $(DESTDIR)$(includecoindir)/OsiScipConfig.h
