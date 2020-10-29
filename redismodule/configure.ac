AC_INIT([redismodule], [0.0.0], [], [], [https://gerrit.oran-osc.org/r/#/admin/projects/ric-plt/dbaas])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIRS([m4])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([run-tests.sh], [chmod +x run-tests.sh])


AM_INIT_AUTOMAKE([-Wall -Werror foreign subdir-objects tar-pax])

m4_ifdef([AM_PROG_AR], [AM_PROG_AR])
LT_INIT([disable-static])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_MAKE_SET


# Checks for header files.

# Checks for typedefs, structures, and compiler characteristics.
AC_HEADER_STDBOOL

AC_CONFIG_FILES([Makefile])

AC_OUTPUT
# Configuration option --with-gcov-report-dir=DIR
#   If this option is given, gcov unit test coverage analysis is enabled and
#   results are copied to the directory.
#
AC_ARG_WITH([gcov-report-dir],
    AS_HELP_STRING([--with-gcov-report-dir=DIR],
        [Directory for GCOV report files]),
    [],
    [with_gcov_report_dir=no])
AC_MSG_CHECKING([gcov])
if test "x$with_gcov_report_dir" = "xno"; then
    AC_MSG_RESULT([no])
    GCOV_REPORT_DIR="gcov_report"
else
    AC_MSG_RESULT([yes])
    AC_MSG_NOTICE([gcov report directory: $with_gcov_report_dir])
    GCOV_REPORT_DIR="$with_gcov_report_dir"
fi
AC_SUBST(GCOV_REPORT_DIR)
AM_CONDITIONAL([ENABLE_GCOV],[test "x$with_gcov_report_dir" != "xno"])
