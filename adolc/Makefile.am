##############################################################################
## Makefile.am -- Process this file with automake to produce Makefile.in
## Revision: $Id: Makefile.am 300 2009-02-26 10:42:44Z awalther $
##
## Copyright (C) Andrea Walther, Andreas Kowarz
##
## This file is part of ADOL-C. This software is provided as open source.
## Any use, reproduction, or distribution of the software constitutes 
## recipient's acceptance of the terms of the accompanying license file.
## 
##############################################################################

if SPARSE
AM_CFLAGS            = @ac_adolc_cflags@ -DADOLC_INTERNAL=1 -DSPARSE=1
AM_CXXFLAGS          = @ac_adolc_cxxflags@ -DADOLC_INTERNAL=1 -DSPARSE=1
else
AM_CFLAGS            = @ac_adolc_cflags@ -DADOLC_INTERNAL=1
AM_CXXFLAGS          = @ac_adolc_cxxflags@ -DADOLC_INTERNAL=1
endif

AM_CPPFLAGS          = -I$(top_srcdir) 

INCLUDES             = -I$(top_builddir)

if SPARSE
SUBDIRS              = drivers sparse tapedoc
else
SUBDIRS              = drivers tapedoc
endif

MAINTAINERCLEANFILES = Makefile.in *~ *.orig adolc_config.h config.h.in

EXTRA_DIST           = uni5_for.c fo_rev.c ho_rev.c \
                       taping_p.h malloc.h \
                       externfcts_p.h checkpointing_p.h buffer_temp.h \
                       Makefile.win

pkginclude_HEADERS   = adolc.h adalloc.h adouble.h adutils.h adutilsc.h \
                       common.h convolut.h dvlparms.h fortutils.h\
                       interfaces.h oplate.h taping.h usrparms.h \
                       externfcts.h checkpointing.h fixpoint.h\
                       adolc_sparse.h adolc_openmp.h \
                       revolve.h

lib_LTLIBRARIES      = libadolc.la

libadolc_la_LDFLAGS  = -version-info 0:0:0

if SPARSE
libadolc_la_SOURCES  = adalloc.c malloc.c adouble.cpp \
                       convolut.c fortutils.c \
                       interfaces.cpp interfacesf.c \
                       taping.c tape_handling.cpp \
                       zos_forward.c fos_forward.c fov_forward.c \
                       hos_forward.c hov_forward.c hov_wk_forward.c \
                       fos_reverse.c fov_reverse.c \
                       hos_reverse.c hos_ov_reverse.c hov_reverse.c \
                       forward_partx.c \
                       externfcts.cpp checkpointing.cpp \
                       fixpoint.cpp fov_offset_forward.c revolve.c \
                       int_forward_s.c int_forward_t.c \
                       indopro_forward_s.c indopro_forward_t.c \
                       nonl_ind_forward_s.c nonl_ind_forward_t.c \
                       int_reverse_s.c int_reverse_t.c 

libadolc_la_LIBADD   = drivers/libdrivers.la sparse/libsparse.la \
                       tapedoc/libtapedoc.la
else
libadolc_la_SOURCES  = adalloc.c malloc.c adouble.cpp \
                       convolut.c fortutils.c\
                       interfaces.cpp interfacesf.c \
                       taping.c tape_handling.cpp \
                       zos_forward.c fos_forward.c fov_forward.c \
                       hos_forward.c hov_forward.c hov_wk_forward.c \
                       fos_reverse.c fov_reverse.c \
                       hos_reverse.c hos_ov_reverse.c hov_reverse.c \
                       forward_partx.c \
                       externfcts.cpp checkpointing.cpp \
                       fixpoint.cpp fov_offset_forward.c revolve.c 

libadolc_la_LIBADD   = drivers/libdrivers.la tapedoc/libtapedoc.la

endif

