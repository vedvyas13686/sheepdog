MAINTAINERCLEANFILES	= Makefile.in

TESTS			= test_util

check_PROGRAMS		= ${TESTS}

AM_CPPFLAGS		= -I$(top_srcdir)/include			\
			  -I$(top_srcdir)/sheep				\
			  -I$(top_srcdir)/lib/tracepoint		\
			  -I../mocks					\
			  -I../cmock/src				\
			  -I../unity/src				\
			  @CHECK_CFLAGS@

LIBS			= -pthread -lm					\
			  @CHECK_LIBS@

test_util_SOURCES	= test_util.c ../../../lib/util.c		\
			  ../mocks/Mocklogger.c				\
			  ../cmock/src/cmock.c ../unity/src/unity.c

clean-local:
	rm -f ${check_PROGRAMS} *.o

coverage:
	@lcov -d . -c -o sheep.info
