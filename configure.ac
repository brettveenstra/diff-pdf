
AC_PREREQ(2.61)
AC_INIT(diff-pdf, 0.1, [vslavik@fastmail.fm])

AC_CONFIG_SRCDIR([diff-pdf.cpp])
AC_CONFIG_AUX_DIR([admin])

AM_INIT_AUTOMAKE
AM_MAINTAINER_MODE

dnl remember, "build" is where we compile, "host" is where the resulting
dnl program runs (which may be different from "build" for cross-compilation)
AC_CANONICAL_HOST


dnl === Program checks ===

AC_PROG_CXX
AC_LANG(C++)

dnl === Library checks ===

PKG_CHECK_MODULES(POPPLER,
                  [poppler-cairo >= 0.10 poppler-glib >= 0.10 cairo-pdf])

AM_OPTIONS_WXCONFIG
AM_PATH_WXCONFIG([2.8.0], [wxfound=1], [wxfound=0], [core,base])
if test "$wxfound" != 1 ; then
    AC_MSG_ERROR([wxWidgets is required])
fi

dnl === Generate output files ===

AC_CONFIG_FILES([
    Makefile
])
AC_OUTPUT