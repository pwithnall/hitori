AC_INIT([Hitori],[3.22.4],[https://gitlab.gnome.org/GNOME/hitori/issues],[hitori],[https://wiki.gnome.org/Apps/Hitori])
AX_IS_RELEASE([git-directory])

AM_INIT_AUTOMAKE([check-news dist-xz no-dist-gzip subdir-objects])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])
AM_MAINTAINER_MODE([enable])

# Options
AX_CHECK_ENABLE_DEBUG([yes],[DEBUG])

AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_CPP
LT_INIT

m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AX_COMPILER_FLAGS([WARN_CFLAGS],[WARN_LDFLAGS])

# Code coverage
AX_CODE_COVERAGE()

# GResources
AC_PATH_PROG([GLIB_COMPILE_RESOURCES],[glib-compile-resources])

# Internationalisation
AM_GNU_GETTEXT([external])
AM_GNU_GETTEXT_VERSION([0.19.8])

# GSettings
GLIB_GSETTINGS

# Documentation
YELP_HELP_INIT

# AppData
APPSTREAM_XML

AX_GENERATE_CHANGELOG

# Dependencies
AC_CHECK_FUNCS([atexit])
PKG_CHECK_MODULES([GENERAL],[
  glib-2.0
  gio-2.0 >= 2.32
  gtk+-3.0 >= 3.15.0
  gmodule-2.0 cairo >= 1.4
])

# GTK+ prefix for gtkbuilder.rng
PKG_CHECK_VAR([GTK_PREFIX],[gtk+-3.0],[prefix])
AC_PATH_PROG([XMLLINT],[xmllint])

# Desktop file validation
AC_PATH_PROG([DESKTOP_FILE_VALIDATE],[desktop-file-validate])

# Output!
AC_CONFIG_FILES([
Makefile
po/Makefile.in
help/Makefile
])
AC_OUTPUT
