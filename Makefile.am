# Makefile.am for uptimed

# this prevents automake from screaming at us about missing README
AUTOMAKE_OPTIONS = foreign

SUBDIRS = libuptimed src man etc

EXTRA_DIST = CREDITS INSTALL.cgi INSTALL.upgrade README.unsupported \
	sample-cgi/uprecords.conf sample-cgi/uprecords.header \
	sample-cgi/uprecords.footer uptimed.spec depcomp

AM_CFLAGS = @CFLAGS@ -DFILE_CONFIG=\"$(sysconfdir)/uptimed.conf\"

install-data-local:
	$(INSTALL) -d $(DESTDIR)/var/spool/uptimed

srpm: dist
	@(rpmbuild -ts uptimed-$(PACKAGE_VERSION).tar.gz)

rpm: dist
	@(rpmbuild -ta uptimed-$(PACKAGE_VERSION).tar.gz)
