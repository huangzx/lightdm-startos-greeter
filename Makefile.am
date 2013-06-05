SUBDIRS = src data po

DISTCLEANFILES = \
	Makefile.in \
	aclocal.m4 \
	configure \
	config.h \
	install-sh \
	missing \
	mkinstalldirs \
	src/Makefile.in \
	po/Makefile.in.in

TMP="/tmp/_rootfs_"

tarinstall:all
	rm -rf $(TMP)
	make install DESTDIR=$(TMP)
	rm -rf $(top_builddir)/rootfs.tar.bz2
	tar jcpf $(top_builddir)/rootfs.tar.bz2 -C $(TMP) .
