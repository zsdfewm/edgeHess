##############################################################################
## Makefile.am -- Process this file with automake to produce Makefile.in
## Revision: $Id: Makefile.am 38 2009-06-17 15:48:09Z awalther $
##
## Copyright (C) Andrea Walther, Andreas Kowarz, Kshitij Kulshreshtha
##
## This file is part of ADOL-C. This software is provided as open source.
## Any use, reproduction, or distribution of the software constitutes 
## recipient's acceptance of the terms of the accompanying license file.
## 
##############################################################################

AUTOMAKE_OPTIONS     = foreign

if DOCEXA
SUBDIRS              = src . test examples
else
if ADDEXA
SUBDIRS              = src . test examples
else
if PAREXA
SUBDIRS              = src . test examples
else
SUBDIRS              = src . test
endif
endif
endif

SUBDIRS += include

MAINTAINERCLEANFILES = Makefile.in 

lib_LTLIBRARIES = lib@adolclib@.la
lib@adolclib@_la_LDFLAGS  = -version-info 3:0:2 -no-undefined
lib@adolclib@_la_SOURCES  = dummy.cpp

lib@adolclib@_la_LIBADD = src/libadolcsrc.la

if BUILD_ADOLC_AMPI_SUPPORT
lib@adolclib@_la_LIBADD  += src/libadolcampi.la
endif

lib@adolclib@_la_LIBADD  += src/drivers/libdrivers.la src/tapedoc/libtapedoc.la

if SPARSE
lib@adolclib@_la_LIBADD   += src/sparse/libsparse.la
endif

lib@adolclib@_la_LIBADD   += src/hessian/libhessian.la
CC = $(saveCC)
CXX = $(saveCXX)

test:
	cd test; $(MAKE) test

.PHONY: test
