AC_INIT(libtuxtxt,2.0.1,,libs)
AM_INIT_AUTOMAKE([foreign])

TUXBOX_APPS
TUXBOX_APPS_DIRECTORY
TUXBOX_APPS_DVB

AC_PROG_CC
AC_PROG_CXX
AC_DISABLE_STATIC
AC_PROG_LIBTOOL
AC_HEADER_STDC

PKG_CHECK_MODULES(FREETYPE, [freetype2])

PKG_CHECK_MODULES(ZLIB, zlib, HAVE_ZLIB="yes", HAVE_ZLIB="no")
AC_SUBST(ZLIB_LIBS)
AC_SUBST(ZLIB_CFLAGS)
if test "$HAVE_ZLIB" = "yes"; then
	AC_DEFINE(HAVE_ZLIB, 1, [zlib available])
fi

AC_ARG_WITH(tuxtxtclearscreen,
	AS_HELP_STRING([--with-tuxtxtclearscreen],[use tuxtxt clear screen, yes or no]),
	[with_tuxtxtclearscreen=$withval],[with_tuxtxtclearscreen=no])
if test x"$with_tuxtxtclearscreen" != xno ; then
	AC_DEFINE(TUXTXT_CLEAR_SCREEN, 1,[define when use tuxtxt clear screen])
fi

AC_OUTPUT([
Makefile
tuxbox-tuxtxt.pc
])
