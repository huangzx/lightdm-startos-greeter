sbin_PROGRAMS = lightdm-startos-greeter

lightdm_startos_greeter_SOURCES = \
	main.c \
	backend.c \
	backend.h \
	gtkclock.c \
	gtkclock.h \
	gtkloginbox.c \
	gtkloginbox.h \
	gtkprompt.c \
	gtkprompt.h \
	gtksysmenu.c \
	gtksysmenu.h \
	gtkuserface.c \
	gtkuserface.h \
	ui.c \
	ui.h 

lightdm_startos_greeter_CFLAGS = \
	-DGETTEXT_PACKAGE=\""$(GETTEXT_PACKAGE)\"" \
	-DLOCALEDIR=\""$(localedir)"\" \
	-DGREETER_DATA_DIR=\""$(pkgdatadir)/"\" \
	-DGREETER_CONF_FILE=\""$(sysconfdir)/lightdm/lightdm-startos-greeter.conf"\" \
	-DTEXTDOMAIN=GETTEXT_PACKAGE \
	-DAPP_NAME=GETTEXT_PACKAGE \
	-Wall \
	$(GREETER_CFLAGS)

lightdm_startos_greeter_LDADD = \
	$(GREETER_LIBS)

startos-greeter-helper.py:startos-greeter-helper.py.in
	sed -e "s|@GREETER_DATA_DIR@|$(pkgdatadir)|g;s|@GREETER_CONF_FILE@|$(sysconfdir)/lightdm/lightdm-startos-greeter.conf|g" $^ > $@

pkgdata_SCRIPTS = startos-greeter-helper.py

DISTCLEANFILES = \
	Makefile.in	\
	startos-greeter-helper.py

clean-local:
	rm -rf startos-greeter-helper.py
