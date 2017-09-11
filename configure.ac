AC_INIT([ch-protos], [0.0.1])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([subdir-objects foreign -Wall -Werror])
AM_SILENT_RULES([yes])
AC_HEADER_STDC
AC_TYPE_SIZE_T
AC_SUBST([AM_CXXFLAGS])
AC_PROG_CC([gcc])
AC_PROG_CXX([g++])
AM_PROG_AR
LT_INIT
AC_CHECK_TOOLS(CXX, [$CCC c++ g++ gcc CC cxx cc++ cl], gcc)
PKG_CHECK_MODULES(PROTOBUF, protobuf >= 3.3.0)
AC_SUBST(PROTOBUF_LIBS)
AC_SUBST(PROTOBUF_CFLAGS)
AC_SUBST(PROTOBUF_VERSION)
AC_LANG([C])

CXXFLAGS="$CXXFLAGS -Wall -std=c++0x"
LIBS="$LIBS"

# ProtoBuf compiler.
# First, specify with --with-protoc=/path/of/protoc.
# Or, specify with env variable PROTOC.
# If neither of the above, find it in the path.
#AC_MSG_CHECKING([for ProtoBuf compiler protoc])
AC_ARG_WITH([protoc],
    [AS_HELP_STRING([--with-protoc=/path/of/protoc],
        [Location of the protocol buffers compiler protoc. Defaults to looking on path.])],
    [PROTOC="$withval"],
    [ AS_IF([test "x${PROTOC}" == "x"],
        [AC_PATH_PROG([PROTOC], [protoc], [no])])
    ]
)
#AC_MSG_RESULT([${PROTOC}])
AS_IF([test "${PROTOC}" == "no"], [AC_MSG_ERROR([ProtoBuf compiler "protoc" not found.])])

AC_SUBST([PROTOC])

AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES(Makefile)
AC_OUTPUT
