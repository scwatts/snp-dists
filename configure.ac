AC_INIT([snp-dists], m4_esyscmd([tr -d '\n' < VERSION]))
AM_INIT_AUTOMAKE([foreign subdir-objects])
AC_CONFIG_SRCDIR([configure.ac])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])

AC_CANONICAL_HOST

PKG_CHECK_MODULES([CHECK],[check >= 0.8.2],[have_check="yes"],
  AC_MSG_WARN(["'Check' unit testing framework not found. It would be impossible to run unit tests!"])
  [have_check="no"])

AC_CHECK_HEADERS([zlib.h])
AX_CHECK_ZLIB

AC_PROG_LIBTOOL
AC_PROG_CC
AC_PROG_CXX

AC_ARG_ENABLE([static-compile], AS_HELP_STRING([--enable-static-compile], [Compile static binary]),
	[case "${enableval}" in
	  no)  static_compile=false ;;
	  *)   static_compile=true ;;
     esac], [static_compile=false])
AM_CONDITIONAL([STATIC_COMPILE], [test "x$static_compile" = "xtrue"])

AC_CONFIG_FILES([Makefile src/Makefile])
AC_OUTPUT
