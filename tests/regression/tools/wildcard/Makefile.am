AM_CFLAGS = -I$(top_srcdir)/include -I$(top_srcdir)/src -I$(top_srcdir)/tests -I$(srcdir) -O2 -g
AM_LDFLAGS =

if LTTNG_TOOLS_BUILD_WITH_LIBDL
LIBS += -ldl
endif
if LTTNG_TOOLS_BUILD_WITH_LIBC_DL
LIBS += -lc
endif

noinst_SCRIPTS = test_event_wildcard
EXTRA_DIST = test_event_wildcard

all-local:
	@if [ x"$(srcdir)" != x"$(builddir)" ]; then \
		for script in $(EXTRA_DIST); do \
			cp -f $(srcdir)/$$script $(builddir); \
		done; \
	fi

clean-local:
	@if [ x"$(srcdir)" != x"$(builddir)" ]; then \
		for script in $(EXTRA_DIST); do \
			rm -f $(builddir)/$$script; \
		done; \
	fi
