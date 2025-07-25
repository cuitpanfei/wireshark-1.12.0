# Makefile.am
# Automake file for Wireshark
#
# Wireshark - Network traffic analyzer
# By Gerald Combs <gerald@wireshark.org>
# Copyright 1998 Gerald Combs
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License
# as published by the Free Software Foundation; either version 2
# of the License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

AM_DISTCHECK_CONFIGURE_FLAGS=@GUI_CONFIGURE_FLAGS@
ACLOCAL_AMFLAGS = `./aclocal-flags`

if HAVE_LIBPY
py_dissectors_dir = -DPYTHON_DIR=\"@pythondir@\"
else
py_dissectors_dir = -DPYTHON_DIR=
endif


if HAVE_WARNINGS_AS_ERRORS
AM_CLEAN_CFLAGS = -Werror
endif

bin_PROGRAMS = \
	@wireshark_bin@		\
	@tshark_bin@		\
	@tfshark_bin@		\
	@text2pcap_bin@		\
	@mergecap_bin@		\
	@capinfos_bin@		\
	@captype_bin@		\
	@editcap_bin@		\
	@randpkt_bin@		\
	@dftest_bin@		\
	@dumpcap_bin@		\
	@reordercap_bin@	\
	@rawshark_bin@		\
	@echld_test_bin@

EXTRA_PROGRAMS = wireshark wireshark-qt tshark tfshark capinfos captype editcap \
	mergecap dftest randpkt text2pcap dumpcap reordercap rawshark \
	wireshark_cxx echld_test

#
# Wireshark configuration files are put in $(pkgdatadir).
#
dist_pkgdata_DATA = COPYING manuf services cfilters colorfilters dfilters \
	smi_modules ipmap.html pdml2html.xsl

#
# Install global profiles in the "profiles" subdirectory
#
profilesdir = $(pkgdatadir)
nobase_dist_profiles_DATA = \
	profiles/Bluetooth/colorfilters \
	profiles/Classic/colorfilters

#
# Install the Diameter DTD and XML files in the "diameter" subdirectory
# of that directory.
#
diameterdir = $(pkgdatadir)/diameter
include diameter/Custom.make
dist_diameter_DATA = $(_CUSTOM_diameter_xml_files_) \
	diameter/chargecontrol.xml \
	diameter/ChinaTelecom.xml \
	diameter/Cisco.xml \
	diameter/Custom.xml \
	diameter/dictionary.dtd \
	diameter/dictionary.xml \
	diameter/eap.xml \
	diameter/Ericsson.xml \
	diameter/etsie2e4.xml \
	diameter/gqpolicy.xml \
	diameter/imscxdx.xml \
	diameter/mobileipv4.xml \
	diameter/mobileipv6.xml \
	diameter/nasreq.xml \
	diameter/sip.xml \
	diameter/Starent.xml \
	diameter/sunping.xml \
	diameter/TGPPGmb.xml \
	diameter/TGPPRx.xml \
	diameter/TGPPS9.xml \
	diameter/TGPPSh.xml \
	diameter/Vodafone.xml \
	diameter/AlcatelLucent.xml \
	diameter/Nokia.xml \
	diameter/NokiaSiemensNetworks.xml \
	diameter/SKT.xml \
	diameter/VerizonWireless.xml

#
# Install the DTDs directory files in the "dtds" subdirectory
# of that directory
#
dtdsdir = $(pkgdatadir)/dtds
dist_dtds_DATA = \
	dtds/dc.dtd \
	dtds/itunes.dtd \
	dtds/mscml.dtd \
	dtds/pocsettings.dtd \
	dtds/presence.dtd \
	dtds/reginfo.dtd \
	dtds/rlmi.dtd \
	dtds/rss.dtd \
	dtds/smil.dtd \
	dtds/xcap-caps.dtd \
	dtds/xcap-error.dtd \
	dtds/watcherinfo.dtd

#
# Install the RADIUS directory files in the "radius" subdirectory
# of that directory.
#
radiusdir = $(pkgdatadir)/radius
include radius/Custom.make
dist_radius_DATA = $(_CUSTOM_radius_dict_) \
	radius/README.radius_dictionary  \
	radius/custom.includes  \
	radius/dictionary  \
	radius/dictionary.3com  \
	radius/dictionary.3gpp  \
	radius/dictionary.3gpp2  \
	radius/dictionary.acc  \
	radius/dictionary.acme \
	radius/dictionary.airespace \
	radius/dictionary.alcatel  \
	radius/dictionary.alcatel.esam \
	radius/dictionary.alcatel.sr \
	radius/dictionary.alcatel-lucent.aaa \
	radius/dictionary.alcatel-lucent.xylan \
	radius/dictionary.alteon  \
	radius/dictionary.altiga  \
	radius/dictionary.alvarion \
	radius/dictionary.apc \
	radius/dictionary.aptis  \
	radius/dictionary.aruba  \
	radius/dictionary.ascend  \
	radius/dictionary.asn \
	radius/dictionary.audiocodes \
	radius/dictionary.avaya \
	radius/dictionary.azaire \
	radius/dictionary.bay  \
	radius/dictionary.bintec  \
	radius/dictionary.bristol  \
	radius/dictionary.cablelabs  \
	radius/dictionary.cabletron  \
	radius/dictionary.chillispot \
	radius/dictionary.cisco  \
	radius/dictionary.cisco.bbsm  \
	radius/dictionary.cisco.vpn3000  \
	radius/dictionary.cisco.vpn5000  \
	radius/dictionary.clavister \
	radius/dictionary.colubris  \
	radius/dictionary.columbia_university  \
	radius/dictionary.compat  \
	radius/dictionary.cosine  \
	radius/dictionary.dhcp \
	radius/dictionary.digium \
	radius/dictionary.eltex \
	radius/dictionary.epygi \
	radius/dictionary.ericsson  \
	radius/dictionary.erx  \
	radius/dictionary.extreme  \
	radius/dictionary.fortinet \
	radius/dictionary.foundry  \
	radius/dictionary.freeradius  \
	radius/dictionary.freeradius.internal  \
	radius/dictionary.freeswitch \
	radius/dictionary.gandalf  \
	radius/dictionary.garderos  \
	radius/dictionary.gemtek  \
	radius/dictionary.h3c \
	radius/dictionary.hp \
	radius/dictionary.huawei \
	radius/dictionary.iea \
	radius/dictionary.infonet \
	radius/dictionary.ipunplugged \
	radius/dictionary.issanni \
	radius/dictionary.itk  \
	radius/dictionary.jradius \
	radius/dictionary.juniper  \
	radius/dictionary.karlnet  \
	radius/dictionary.lancom \
	radius/dictionary.livingston  \
	radius/dictionary.localweb  \
	radius/dictionary.lucent \
	radius/dictionary.manzara \
	radius/dictionary.merit  \
	radius/dictionary.microsoft  \
	radius/dictionary.mikrotik  \
	radius/dictionary.motorola \
	radius/dictionary.motorola.wimax \
	radius/dictionary.navini  \
	radius/dictionary.netscreen  \
	radius/dictionary.networkphysics \
	radius/dictionary.nexans \
	radius/dictionary.nokia  \
	radius/dictionary.nokia.conflict \
	radius/dictionary.nomadix  \
	radius/dictionary.nortel \
	radius/dictionary.ntua \
	radius/dictionary.openser \
	radius/dictionary.packeteer \
	radius/dictionary.patton \
	radius/dictionary.propel  \
	radius/dictionary.prosoft \
	radius/dictionary.quiconnect \
	radius/dictionary.quintum  \
	radius/dictionary.redback  \
	radius/dictionary.redcreek  \
	radius/dictionary.rfc2865 \
	radius/dictionary.rfc2866 \
	radius/dictionary.rfc2867 \
	radius/dictionary.rfc2868 \
	radius/dictionary.rfc2869 \
	radius/dictionary.rfc3162 \
	radius/dictionary.rfc3576 \
	radius/dictionary.rfc3580 \
	radius/dictionary.rfc4072 \
	radius/dictionary.rfc4372 \
	radius/dictionary.rfc4603 \
	radius/dictionary.rfc4675 \
	radius/dictionary.rfc4679 \
	radius/dictionary.rfc4818 \
	radius/dictionary.rfc4849 \
	radius/dictionary.rfc5090 \
	radius/dictionary.rfc5176 \
	radius/dictionary.rfc5447 \
	radius/dictionary.rfc5580 \
	radius/dictionary.rfc5607 \
	radius/dictionary.rfc5904 \
	radius/dictionary.rfc6519 \
	radius/dictionary.rfc6572 \
	radius/dictionary.riverstone \
	radius/dictionary.roaringpenguin \
	radius/dictionary.shasta  \
	radius/dictionary.shiva  \
	radius/dictionary.slipstream \
	radius/dictionary.sofaware \
	radius/dictionary.sonicwall  \
	radius/dictionary.springtide  \
	radius/dictionary.starent  \
	radius/dictionary.t_systems_nova  \
	radius/dictionary.telebit  \
	radius/dictionary.telkom \
	radius/dictionary.trapeze  \
	radius/dictionary.tropos \
	radius/dictionary.ukerna  \
	radius/dictionary.unix  \
	radius/dictionary.usr  \
	radius/dictionary.utstarcom \
	radius/dictionary.valemount  \
	radius/dictionary.versanet  \
	radius/dictionary.vqp \
	radius/dictionary.walabi \
	radius/dictionary.waverider \
	radius/dictionary.wichorus \
	radius/dictionary.wimax  \
	radius/dictionary.wimax.wichorus \
	radius/dictionary.wispr  \
	radius/dictionary.xedia \
	radius/dictionary.zyxel

#
# Install the tpncp directory files in the "tpncp" subdirectory
# of that directory
#
tpncpdir = $(pkgdatadir)/tpncp
dist_tpncp_DATA = \
	tpncp/tpncp.dat

#
# Install the wimaxasncp directory files in the "wimaxasncp" subdirectory
# of that directory
#
wimaxasncpdir = $(pkgdatadir)/wimaxasncp
dist_wimaxasncp_DATA = \
	wimaxasncp/dictionary.xml \
	wimaxasncp/dictionary.dtd

PLATFORM_PCAP_SRC = \
	capture-pcap-util-unix.c

if HAVE_PLUGINS
-include plugins/Custom.make
plugin_ldadd = $(_CUSTOM_plugin_ldadd_) \
	-dlopen plugins/docsis/docsis.la \
	-dlopen plugins/ethercat/ethercat.la \
	-dlopen plugins/gryphon/gryphon.la \
	-dlopen plugins/irda/irda.la \
	-dlopen plugins/m2m/m2m.la \
	-dlopen plugins/mate/mate.la \
	-dlopen plugins/opcua/opcua.la \
	-dlopen plugins/profinet/profinet.la \
	-dlopen plugins/stats_tree/stats_tree.la \
	-dlopen plugins/unistim/unistim.la \
	-dlopen plugins/wimax/wimax.la \
	-dlopen plugins/wimaxmacphy/wimaxmacphy.la

else		# HAVE_PLUGINS

plugin_ldadd =

endif		# HAVE_PLUGINS

include Makefile.common

if ENABLE_STATIC
if HAVE_GTK
wireshark_LDFLAGS = -Wl,-static -all-static
endif
if HAVE_Qt
wireshark_qt_LDFLAGS = -Wl,-static -all-static
endif
else
if HAVE_GTK
wireshark_LDFLAGS = -export-dynamic
endif
if HAVE_Qt
wireshark_qt_LDFLAGS = -export-dynamic
endif
endif

# Libraries and plugin flags with which to link wireshark.
#
# Note that Wireshark, when built with a version of GTK+ that runs
# atop X11, doesn't have to be linked with @SOCKET_LIBS@ or @NSL_LIBS@,
# as those should also be included in @GTK_LIBS@ (as those are also
# needed for X applications, and GTK+ applications are X applications
# if the version of GTK+ they're built with runs atop X11).
#
# However, it *does* have to be linked with @GLIB_LIBS@; not all of
# the necessary GLib libraries are included in @GTK_LIBS@.  To quote
# Gentoo bug 423743 at
#
#	https://bugs.gentoo.org/show_bug.cgi?id=423743
#
# "The Makefile.am claims including GLIB_LIBS when linking wireshark is
# unnecessary, because wireshark links to GTK_LIBS which is a superset.
# It is not actually a superset: gmodule is included in GLIB_LIBS but
# not in GTK_LIBS (unless accidentally on older glibs/gtks)."
#
# although it's also possible that -lgmodule is in GTK_LIBS but not
# GLIB_LIBS (that's the case on my machine right now, for example).
#
wireshark_ldadd = \
	ui/libui.a			\
	ui/libui_dirty.a		\
	codecs/libcodec.a		\
	filetap/libfiletap.la		\
	wiretap/libwiretap.la		\
	epan/libwireshark.la		\
	wsutil/libwsutil.la		\
	@SSL_LIBS@			\
	$(plugin_ldadd)			\
	@PCAP_LIBS@			\
	@C_ARES_LIBS@			\
	@ADNS_LIBS@			\
	@KRB5_LIBS@			\
	@APPLICATIONSERVICES_FRAMEWORKS@	\
	@SYSTEMCONFIGURATION_FRAMEWORKS@	\
	@COREFOUNDATION_FRAMEWORKS@	\
	@PY_LIBS@			\
	@LIBGCRYPT_LIBS@		\
	@LIBGNUTLS_LIBS@		\
	@LIBSMI_LDFLAGS@		\
	@PORTAUDIO_LIBS@		\
	@GLIB_LIBS@			\
	-lm

if HAVE_Qt
wireshark_qt_SOURCES = $(WIRESHARK_COMMON_SRC)
wireshark_qt_INCLUDES = $(WIRESHARK_COMMON_INCLUDES)
wireshark_qt_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)
wireshark_qt_LDADD = \
	ui/qt/libqtui.a \
	$(wireshark_ldadd) \
	@Qt_LIBS@

#
# XXX - this makes wireshark_qt_LDFLAGS not work; we should figure out
# another way to get wireshark-qt linked as a C++ program, perhaps by
# having a top-level wireshark-qt.cpp file that contains main() and
# hthat calls the UI code from ui/qt.
#
wireshark_qt_LINK = $(CXXLINK)
endif

if HAVE_GTK
wireshark_SOURCES = $(WIRESHARK_COMMON_SRC)
wireshark_INCLUDES = $(WIRESHARK_COMMON_INCLUDES)
wireshark_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)
wireshark_LDADD = \
	ui/gtk/libgtkui.a \
	$(wireshark_ldadd) \
	@GTK_LIBS@
endif

# Ideally we could trigger automatic c++ linking here with
#   nodist_EXTRA_wireshark_SOURCES = dummy.cpp
# Unfortunately that check is done by automake and not configure.
# We do the following to try to avoid using c++ to link Wireshark at
# all times.
nodist_EXTRA_wireshark_cxx_SOURCES = dummy.cpp
wireshark_cxx_SOURCES =

if ENABLE_STATIC
tshark_LDFLAGS = -Wl,-static -all-static
else
tshark_LDFLAGS = -export-dynamic
endif

# Libraries and plugin flags with which to link tshark.
tshark_LDADD = \
	ui/cli/libcliui.a		\
	ui/libui.a			\
	wiretap/libwiretap.la		\
	epan/libwireshark.la		\
	wsutil/libwsutil.la		\
	@SSL_LIBS@			\
	$(plugin_ldadd)			\
	@GLIB_LIBS@			\
	@PCAP_LIBS@			\
	@SOCKET_LIBS@			\
	@NSL_LIBS@			\
	@C_ARES_LIBS@			\
	@ADNS_LIBS@			\
	@KRB5_LIBS@			\
	@SYSTEMCONFIGURATION_FRAMEWORKS@	\
	@COREFOUNDATION_FRAMEWORKS@	\
	@PY_LIBS@			\
	@LIBGCRYPT_LIBS@		\
	@LIBGNUTLS_LIBS@		\
	@LIBSMI_LDFLAGS@		\
	-lm
tshark_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)

if ENABLE_STATIC
tfshark_LDFLAGS = -Wl,-static -all-static
else
tfshark_LDFLAGS = -export-dynamic
endif

# Libraries and plugin flags with which to link tfshark.
tfshark_LDADD = \
	ui/cli/libcliui.a		\
	ui/libui.a			\
	filetap/libfiletap.la		\
	wiretap/libwiretap.la		\
	epan/libwireshark.la		\
	wsutil/libwsutil.la		\
	@SSL_LIBS@			\
	$(plugin_ldadd)			\
	@GLIB_LIBS@			\
	@PCAP_LIBS@			\
	@SOCKET_LIBS@			\
	@NSL_LIBS@			\
	@KRB5_LIBS@			\
	@SYSTEMCONFIGURATION_FRAMEWORKS@	\
	@COREFOUNDATION_FRAMEWORKS@	\
	@PY_LIBS@			\
	@LIBGNUTLS_LIBS@		\
	@LIBSMI_LDFLAGS@		\
	-lm
tfshark_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)

if ENABLE_STATIC
rawshark_LDFLAGS = -Wl,-static -all-static
else
rawshark_LDFLAGS = -export-dynamic
endif

# Libraries and plugin flags with which to link rawshark.
rawshark_LDADD = \
	ui/libui.a			\
	wiretap/libwiretap.la		\
	epan/libwireshark.la		\
	wsutil/libwsutil.la		\
	@SSL_LIBS@			\
	$(plugin_ldadd)			\
	@GLIB_LIBS@			\
	@PCAP_LIBS@			\
	@SOCKET_LIBS@			\
	@NSL_LIBS@			\
	@C_ARES_LIBS@			\
	@ADNS_LIBS@			\
	@KRB5_LIBS@			\
	@SYSTEMCONFIGURATION_FRAMEWORKS@	\
	@COREFOUNDATION_FRAMEWORKS@	\
	@PY_LIBS@			\
	@LIBGCRYPT_LIBS@		\
	@LIBGNUTLS_LIBS@		\
	@LIBSMI_LDFLAGS@		\
	-lm
rawshark_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)

# Libraries with which to link text2pcap.
text2pcap_LDADD = \
	wsutil/libwsutil.la		\
	@GLIB_LIBS@			\
	-lm
# Don't turn on -Werror for text2pcap: its source includes text2pcap-scanner.c
# which is generated (and therefore not always clean).
# We could generate text2pcap.o as a library with -Werror but for now it
# doesn't seem worth the effort.
#text2pcap_CFLAGS = $(AM_CLEAN_CFLAGS)

# Libraries with which to link mergecap.
mergecap_LDADD = \
	wiretap/libwiretap.la		\
	wsutil/libwsutil.la		\
	@GLIB_LIBS@
mergecap_CFLAGS = $(AM_CLEAN_CFLAGS)

# Libraries with which to link capinfos.
capinfos_LDADD = \
	wiretap/libwiretap.la		\
	wsutil/libwsutil.la		\
	@GLIB_LIBS@			\
	@LIBGCRYPT_LIBS@
capinfos_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)

# Libraries with which to link captype.
captype_LDADD = \
	wiretap/libwiretap.la		\
	wsutil/libwsutil.la		\
	@GLIB_LIBS@
captype_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)

# Libraries with which to link editcap.
editcap_LDADD = \
	wiretap/libwiretap.la		\
	wsutil/libwsutil.la		\
	@GLIB_LIBS@
editcap_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)

# Libraries with which to link reordercap.
reordercap_LDADD = \
	wiretap/libwiretap.la		\
	wsutil/libwsutil.la		\
	@GLIB_LIBS@
reordercap_CFLAGS = $(AM_CLEAN_CFLAGS)

# Libraries with which to link randpkt.
randpkt_LDADD = \
	wiretap/libwiretap.la		\
	wsutil/libwsutil.la		\
	@GLIB_LIBS@			\
	@PCAP_LIBS@			\
	@SOCKET_LIBS@			\
	@NSL_LIBS@			\
	@C_ARES_LIBS@			\
	@ADNS_LIBS@			\
	-lm
randpkt_CFLAGS = $(AM_CLEAN_CFLAGS)

# Libraries and plugin flags with which to link dftest.
dftest_LDADD = \
	ui/libui.a			\
	wiretap/libwiretap.la		\
	wsutil/libwsutil.la		\
	epan/libwireshark.la		\
	@SSL_LIBS@			\
	$(plugin_ldadd)			\
	@GLIB_LIBS@			\
	@PCAP_LIBS@			\
	@SOCKET_LIBS@			\
	@NSL_LIBS@			\
	@C_ARES_LIBS@			\
	@ADNS_LIBS@			\
	@KRB5_LIBS@			\
	@PY_LIBS@			\
	@LIBGCRYPT_LIBS@		\
	@LIBGNUTLS_LIBS@		\
	@LIBSMI_LDFLAGS@		\
	-lm
dftest_CFLAGS = $(AM_CLEAN_CFLAGS) $(py_dissectors_dir)

echld_test_LDADD = \
	epan/libwireshark.la		\
	echld/libechld.la		\
	wsutil/libwsutil.la		\
	@GLIB_LIBS@			\
	@PCAP_LIBS@			\
	@SOCKET_LIBS@			\
	@NSL_LIBS@			\
	@C_ARES_LIBS@			\
	@ADNS_LIBS@			\
	-lm

echld_test_DEPENDENCIES = \
	echld/libechld.la \
	epan/libwireshark.la

echld_test_CFLAGS = $(AM_CLEAN_CFLAGS)


# Libraries with which to link dumpcap.
dumpcap_LDADD = \
	wsutil/libwsutil.la		\
	@GLIB_LIBS@			\
	@PCAP_LIBS@			\
	@SOCKET_LIBS@			\
	@NSL_LIBS@			\
	@SYSTEMCONFIGURATION_FRAMEWORKS@	\
	@COREFOUNDATION_FRAMEWORKS@	\
	@LIBCAP_LIBS@
dumpcap_CFLAGS = $(AM_CLEAN_CFLAGS) $(PIE_CFLAGS)
dumpcap_LDFLAGS = $(PIE_LDFLAGS)

# Common headers
AM_CPPFLAGS = -I$(top_srcdir) -I$(top_srcdir)/wiretap \
	$(LIBGNUTLS_CFLAGS) $(LIBGCRYPT_CFLAGS) $(LIBSMI_CFLAGS) $(PY_CFLAGS) \
	@LUA_INCLUDES@ -DTOP_SRCDIR=\"$(abs_top_srcdir)\"

#
# Build the version string
#
# FORCE is the portable version of .PHONY
FORCE:

AM_V_PERL = $(am__v_PERL_@AM_V@)
am__v_PERL_ = $(am__v_PERL_@AM_DEFAULT_V@)
am__v_PERL_0 = @echo "  PERL    " $@;
am__v_PERL_1 =

version.h: FORCE
	$(AM_V_PERL)$(PERL) $(srcdir)/make-version.pl $(srcdir)

#
# Build shell scripts by doing variable substitution.
# Taken from autoconf 2.13.
#
editsh = sed -e 's,@''SHELL''@,$(SHELL),g'

SUFFIXES = .sh
.sh:
	rm -f $@ $@.tmp
	$(editsh) $< > $@.tmp && chmod +x $@.tmp && mv $@.tmp $@

services:
	$(PYTHON) $(srcdir)/tools/make-services.py

CLEANFILES =		\
	*~		\
	doxygen-core.tag	\
	vgcore.*

#
# We have to remove version.h with "make distclean", as, otherwise,
# "make distcheck" fails.  We still need to make the tarballs work
# even if you do "make distclean" and try to rebuild; that's a work in
# progress.
#
# XXX - "ps.c" is distributed in the source tarballs; why is it in the
# list of files removed by "make distclean"?  (It's deliberately
# included in that list.)
#
DISTCLEANFILES = \
	ps.c			\
	version.h

MAINTAINERCLEANFILES =		\
	$(GENERATED_FILES)	\
	Makefile.in		\
	aclocal.m4		\
	compile			\
	config.h.in		\
	configure		\
	depcomp			\
	install-sh		\
	ltmain.sh		\
	missing			\
	ylwrap

EXTRA_DIST = \
	INSTALL.configure	\
	Makefile.am.inc		\
	Makefile.common		\
	Makefile.nmake		\
	Makefile.nmake.inc	\
	README.aix		\
	README.bsd		\
	README.DECT		\
	README.hpux		\
	README.irix		\
	README.linux		\
	README.macos		\
	README.tru64		\
	README.vmware		\
	README.windows		\
	abi-descriptor.template	\
	aclocal-fallback/libsmi.m4 \
	aclocal-fallback/libgcrypt.m4 \
	aclocal-fallback/glib-2.0.m4 \
	aclocal-fallback/gtk-2.0.m4 \
	aclocal-fallback/gtk-3.0.m4 \
	aclocal-flags		\
	adns_dll.dep		\
	adns_dll.rc		\
	autogen.sh		\
	capinfos.c		\
	captype.c		\
	capture_win_ifnames.c	\
	capture_win_ifnames.h	\
	capture-wpcap.c		\
	capture-wpcap.h		\
	capture_wpcap_packet.c  \
	capture_wpcap_packet.h  \
	cfilters		\
	colorfilters		\
	config.h.win32		\
	config.nmake		\
	debian/changelog	\
	debian/compat		\
	debian/control		\
	debian/copyright	\
	debian/dirs		\
	debian/headers-check.c	\
	debian/postinst		\
	debian/rules		\
	debian/tshark.manpages	\
	debian/wireshark-common.manpages \
	debian/wireshark-dev.docs \
	debian/wireshark-dev.manpages \
	debian/wireshark-dev.prerm \
	debian/wireshark.manpages \
	debian/wireshark.menu	\
	dfilters		\
	doxygen.cfg.in		\
	dumpcap.c	\
	editcap.c		\
	epan/print.ps		\
	filetap/CMakeLists.txt	\
	fix/FIX.xml		\
	fix/FIX40.xml		\
	fix/FIX41.xml		\
	fix/FIX42.xml		\
	fix/FIX43.xml		\
	fix/FIX44.xml		\
	fix/README		\
	fix/Values.xsl		\
	fix/hfDecl.xsl		\
	fix/hfField.xsl		\
	fix/hfList.xsl		\
	idl/coseventcomm.idl	\
	idl/cosnaming.idl	\
	idl/tango.idl	\
	idl/parlay/am.idl	\
	idl/parlay/cccs.idl	\
	idl/parlay/cm.idl	\
	idl/parlay/common_cc_data.idl	\
	idl/parlay/cs.idl	\
	idl/parlay/dsc.idl	\
	idl/parlay/fw_data.idl	\
	idl/parlay/fw_if.idl	\
	idl/parlay/fw_if_access.idl	\
	idl/parlay/fw_if_app.idl	\
	idl/parlay/fw_if_entop.idl	\
	idl/parlay/fw_if_service.idl	\
	idl/parlay/gcc_data.idl	\
	idl/parlay/gcc_interfaces.idl	\
	idl/parlay/gms.idl	\
	idl/parlay/mm.idl	\
	idl/parlay/mmccs.idl	\
	idl/parlay/mmm.idl	\
	idl/parlay/mpcc_data.idl	\
	idl/parlay/mpcc_interfaces.idl	\
	idl/parlay/osa.idl	\
	idl/parlay/pam_data.idl	\
	idl/parlay/pam_interfaces.idl	\
	idl/parlay/Parlay.idl	\
	idl/parlay/policy_data.idl	\
	idl/parlay/policy_interfaces.idl	\
	idl/parlay/README.parlay	\
	idl/parlay/termcap.idl	\
	idl/parlay/ui_data.idl	\
	idl/parlay/ui_interfaces.idl	\
	image/capinfos.rc.in	\
	image/captype.rc.in	\
	image/capture_comment.svg	\
	image/capture_comment_add.png	\
	image/capture_comment_disabled.png	\
	image/capture_comment_update.png	\
	image/capture_start_24.png		\
	image/capture_start_active_24.png	\
	image/capture_stop_24.png		\
	image/clist_ascend.xpm			\
	image/clist_descend.xpm			\
	image/copy-8.png			\
	image/dfilter_apply_disabled.png	\
	image/dfilter_apply_hover.png		\
	image/dfilter_apply_normal.png		\
	image/dfilter_apply_pressed.png		\
	image/dfilter_bookmark_disabled.png	\
	image/dfilter_bookmark_hover.png	\
	image/dfilter_bookmark_normal.png	\
	image/dfilter_bookmark_pressed.png	\
	image/dfilter_dropdown.png		\
	image/dfilter_erase_active.png		\
	image/dfilter_erase_normal.png		\
	image/dfilter_erase_selected.png	\
	image/dfilter_refresh_active.png	\
	image/dfilter_refresh_normal.png	\
	image/display_filter.qrc		\
	image/dumpcap.rc.in	\
	image/editcap.rc.in	\
	image/expert_chat.png	\
	image/expert_error.png	\
	image/expert_indicators.svg	\
	image/expert_none.png	\
	image/expert_note.png	\
	image/expert_warn.png	\
	image/file_dlg_win32.rc \
	image/filetap.rc.in	\
	image/hi16-app-wireshark.png	\
	image/hi32-app-wireshark.png	\
	image/hi48-app-wireshark.png	\
	image/layout_1.png		\
	image/layout_2.png		\
	image/layout_3.png		\
	image/layout_4.png		\
	image/layout_5.png		\
	image/layout_6.png		\
	image/libwireshark.rc.in	\
	image/libwsutil.rc.in		\
	image/lo16-app-wireshark.png	\
	image/lo32-app-wireshark.png	\
	image/lo48-app-wireshark.png	\
	image/Makefile.nmake			\
	image/mergecap.rc.in			\
	image/minus-8.png			\
	image/nsis-checked.bmp			\
	image/nsis-unchecked.bmp		\
	image/openhand-16.png			\
	image/plus-8.png			\
	image/rawshark.rc.in			\
	image/README.image			\
	image/reordercap.rc.in			\
	image/rubberband-16.png			\
	image/status.qrc			\
	image/stock_dialog_error_48.xpm		\
	image/stock_dialog_info_48.xpm		\
	image/stock_dialog_question_48.xpm	\
	image/stock_dialog_stop_48.xpm		\
	image/stock_dialog_warning_48.xpm	\
	image/text2pcap.rc.in			\
	image/tfshark.rc.in			\
	image/toolbar.qrc			\
	image/toolbar/analyze_24.xpm 		\
	image/toolbar/audio_player_24.xpm	\
	image/toolbar/autoscroll_24.xpm		\
	image/toolbar/capture_airpcap_16.xpm	\
	image/toolbar/capture_capture_16.xpm	\
	image/toolbar/capture_details_16.xpm	\
	image/toolbar/capture_details_24.xpm	\
	image/toolbar/capture_ethernet_16.xpm	\
	image/toolbar/capture_filter_24.xpm	\
	image/toolbar/capture_interfaces_16.png	\
	image/toolbar/capture_interfaces_24.png	\
	image/toolbar/capture_options_16.png	\
	image/toolbar/capture_options_24.png	\
	image/toolbar/capture_prepare_16.xpm	\
	image/toolbar/capture_restart_16.png	\
	image/toolbar/capture_restart_24.png	\
	image/toolbar/capture_start_16.png	\
	image/toolbar/capture_start_24.png	\
	image/toolbar/capture_stop_16.png	\
	image/toolbar/capture_stop_24.png	\
	image/toolbar/checkbox_16.xpm		\
	image/toolbar/colorize_24.xpm		\
	image/toolbar/conversations_16.xpm	\
	image/toolbar/decode_24.xpm		\
	image/toolbar/decode_as_16.xpm		\
	image/toolbar/display_filter_24.xpm	\
	image/toolbar/endpoints_16.xpm		\
	image/toolbar/expert_info_16.xpm	\
	image/toolbar/file_set_list_16.xpm	\
	image/toolbar/file_set_next_16.xpm	\
	image/toolbar/file_set_previous_16.xpm	\
	image/toolbar/flow_graph_16.xpm	\
	image/toolbar/gnome_emblem_web_16.png	\
	image/toolbar/gnome_emblem_web_24.png	\
	image/toolbar/graphs_16.xpm	\
	image/toolbar/icon_color_0.xpm	\
	image/toolbar/icon_color_1.xpm	\
	image/toolbar/icon_color_2.xpm	\
	image/toolbar/icon_color_3.xpm	\
	image/toolbar/icon_color_4.xpm	\
	image/toolbar/icon_color_5.xpm	\
	image/toolbar/icon_color_6.xpm	\
	image/toolbar/icon_color_7.xpm	\
	image/toolbar/icon_color_8.xpm	\
	image/toolbar/icon_color_9.xpm	\
	image/toolbar/internet_24.xpm	\
	image/toolbar/modem_16.png	\
	image/toolbar/modem_16.xpm	\
	image/toolbar/network_bluetooth_16.png	\
	image/toolbar/network_usb.svg		\
	image/toolbar/network_usb_16.png	\
	image/toolbar/network_virtual_16.xpm	\
	image/toolbar/network_wired_16.png	\
	image/toolbar/network_wireless_16.png	\
	image/toolbar/pipe_16.png	\
	image/toolbar/remote_arrow_16.png	\
	image/toolbar/remote_globe_16.png	\
	image/toolbar/remote_sat_16.png	\
	image/toolbar/resize_columns_24.xpm	\
	image/toolbar/telephone_16.xpm	\
	image/toolbar/telephony_16.xpm	\
	image/toolbar/time_24.xpm	\
	image/toolbar/toolbar_wireshark_file_16.png	\
	image/toolbar/toolbar_wireshark_file_24.png	\
	image/toolbar/voip_flow_24.xpm	\
	image/toolbar/web_support_24.xpm	\
	image/toolbar/wep_closed_24.xpm \
	image/tshark.rc.in	\
	image/voip_select.xpm	\
	image/wireshark.exe.manifest.in \
	image/wireshark.ico	\
	image/wireshark.rc.in	\
	image/wiresharkdoc.ico	\
	image/wiresharkinst.ico	\
	image/WiresharkDoc-16.png	\
	image/WiresharkDoc-24.png	\
	image/WiresharkDoc-32.png	\
	image/WiresharkDoc-48.png	\
	image/WiresharkDoc-64.png	\
	image/WiresharkDoc-128.png	\
	image/WiresharkDoc-256.png	\
	image/wiretap.rc.in	\
	image/wsicon.svg	\
	image/wsicon16.png	\
	image/wsicon24.png	\
	image/wsicon32.png	\
	image/wsicon48.png	\
	image/wsicon64.png	\
	image/wsicon128.png	\
	image/wsicon256.png	\
	image/wsicon512.png	\
	image/wsicon1024.png	\
	image/wsicon-ask.png	\
	image/wsicon-ask.svg	\
	image/wsiconcap.svg	\
	image/wsiconcap256.png	\
	image/wsiconcap512.png	\
	image/wsiconcap1024.png	\
	image/wsiconinst.svg	\
	image/wsiconinst256.png	\
	image/wslogo-dev.svg	\
	image/wslogo.eps	\
	image/wslogo.svg	\
	image/wssplash_dev.png	\
	image/wssplash.png	\
	ipmap.html		\
	macosx-setup.sh		\
        macosx-support-lib-patches/glib-gconvert.c.patch \
	macosx-support-lib-patches/glib-pkgconfig.patch \
	macosx-support-lib-patches/gnutls-pkgconfig.patch \
	macosx-support-lib-patches/portaudio-pa_mac_core.h.patch \
	macosx-support-lib-patches/portaudio-pa_mac_core.c.patch \
	make-version.pl		\
	manuf			\
	manuf.tmpl		\
	mergecap.c		\
	pdml2html.xsl		\
	reordercap.c		\
	smi_modules		\
	text2pcap-scanner.l	\
	text2pcap.h		\
	services		\
	wireshark.desktop	\
	wireshark-mime-package.xml \
	wka.tmpl		\
	CMakeLists.txt		\
	cmakeconfig.h.in	\
	wsutil/CMakeLists.txt	\
	CMakeOptions.txt	\
	wiretap/CMakeLists.txt	\
	README.cmake		\
	ConfigureChecks.cmake	\
	cmake/modules/CMakeInstallDirs.cmake	\
	cmake/modules/COPYING-CMAKE-SCRIPTS	\
	cmake/modules/CheckCLinkerFlag.cmake	\
	cmake/modules/FeatureSummary.cmake	\
	cmake/modules/FindADNS.cmake		\
	cmake/modules/FindCAP.cmake		\
	cmake/modules/FindCARES.cmake		\
	cmake/modules/FindFOP.cmake		\
	cmake/modules/FindGCRYPT.cmake		\
	cmake/modules/FindGEOIP.cmake		\
	cmake/modules/FindGLIB2.cmake		\
	cmake/modules/FindGMODULE2.cmake	\
	cmake/modules/FindGNUTLS.cmake		\
	cmake/modules/FindGTHREAD2.cmake	\
	cmake/modules/FindGTK2.cmake		\
	cmake/modules/FindGTK3.cmake		\
	cmake/modules/FindHtmlViewer.cmake	\
	cmake/modules/FindKERBEROS.cmake	\
	cmake/modules/FindNL.cmake		\
	cmake/modules/FindLEX.cmake		\
	cmake/modules/FindLUA.cmake		\
	cmake/modules/FindLYNX.cmake		\
	cmake/modules/FindM.cmake		\
	cmake/modules/FindPCAP.cmake		\
	cmake/modules/FindPOD.cmake		\
	cmake/modules/FindPORTAUDIO.cmake	\
	cmake/modules/FindSED.cmake		\
	cmake/modules/FindSH.cmake		\
	cmake/modules/FindSMI.cmake		\
	cmake/modules/FindXMLLINT.cmake		\
	cmake/modules/FindXSLTPROC.cmake	\
	cmake/modules/FindYACC.cmake		\
	cmake/modules/FindYAPP.cmake		\
	cmake/modules/FindZLIB.cmake		\
	cmake/modules/LICENSE.txt		\
	cmake/modules/UseLemon.cmake		\
	cmake/modules/UseMakeDissectorReg.cmake	\
	cmake/modules/UseMakeTapReg.cmake	\
	cmake/modules/readme.txt		\
	ui/win32/Makefile.nmake			\
	ui/win32/console_win32.c		\
	ui/win32/console_win32.h		\
	ui/win32/file_dlg_win32.c		\
	ui/win32/file_dlg_win32.h		\
	ui/win32/print_win32.c			\
	ui/win32/print_win32.h			\
	ui/win32/settings.ini			\
	CPackConfig.txt

install-exec-hook:
if HAVE_DUMPCAP_GROUP
	chgrp $(DUMPCAP_GROUP) $(DESTDIR)$(bindir)/dumpcap
endif
if SETCAP_INSTALL
	$(SETCAP) cap_net_raw,cap_net_admin+ep $(DESTDIR)$(bindir)/dumpcap
	chmod o-rws $(DESTDIR)$(bindir)/dumpcap
else
if SETUID_INSTALL
	chmod o-rws $(DESTDIR)$(bindir)/dumpcap
	chmod +s $(DESTDIR)$(bindir)/dumpcap
endif
endif


DIST_SUBDIRS = asn1 codecs doc epan echld filetap ui ui/cli ui/gtk ui/qt help packaging plugins tools wiretap wsutil docbook

if HAVE_PLUGINS
SUBDIRS = tools wsutil wiretap filetap epan @echld_dir@ plugins packaging help ui @wireshark_SUBDIRS@ ui/cli . doc
else
SUBDIRS = tools wsutil wiretap filetap epan @echld_dir@ packaging help ui @wireshark_SUBDIRS@ ui/cli . doc
endif

help/faq.txt: $(srcdir)/help/faq.py
	$(AM_V_GEN)(cd help ; \
	$(MAKE) faq.txt ;)

libtool: $(LIBTOOL_DEPS)
	$(SHELL) ./config.status --recheck


# Used by patch-bzip2
# Trim off any extra version information and find the previous micro release.
BASE_VERSION=`echo "$(VERSION)" | awk -F. '{$$3 = $$3 + 0 ; printf("%d.%d.%d"), $$1, $$2, $$3}'`
PREV_VERSION=`echo "$(VERSION)" | awk -F. '{$$3 = $$3 + 0 ; if ($$3 > 0) $$3-- ; printf("%d.%d.%d"), $$1, $$2, $$3}'`
PREV_DIR="wireshark-$(PREV_VERSION)"
PREV_FILE="$(PREV_DIR).tar.bz2"
PREV_URL="http://www.wireshark.org/download/src/all-versions/$(PREV_FILE)"

patch-bzip2: distdir
	if test x$(BASE_VERSION) != x$(PREV_VERSION) ; then \
		curl -z $(PREV_FILE) -o $(PREV_FILE) $(PREV_URL) && \
		tar -xjf $(PREV_FILE) && \
		diff -urN $(PREV_DIR) $(distdir) | bzip2 > patch-wireshark-$(PREV_VERSION)-to-$(VERSION).bz2 && \
		echo "Created patch-bzip2" ; \
		rm -rf "$(PREV_FILE)" "$(PREV_DIR)" ; \
	else \
		echo "This appears to be the first micro version ($(PREV_VERSION)). Skipping." ; \
	fi
	$(am__remove_distdir)

# Install some desktop files (for use with GNOME, KDE, or any other freedesktop.org-compliant desktops)
# No, these do not go into $(datarootdir): the desktop won't look for them there.
# Yes, that violate's autofoo's principle of relocatability.
# What we (probably) should do is check `pkg-config --variable=prefix gtk+-2.0` to know where
# to install this stuff...
#
# Do not use the -T flag to the install command, as it's not portable.
# Some versions of install don't support a -T flag at all, and the
# FreeBSD install command has a -T flag that takes an argument and
# that has completely different semantics.
install_desktop_files:
	mkdir -p $(DESTDIR)/usr/share/{mime/packages,applications}
	install -m 644 $(srcdir)/wireshark-mime-package.xml $(DESTDIR)/usr/share/mime/packages/wireshark.xml
	if test x$(DESKTOP_FILE_INSTALL) != x ; then \
		$(DESKTOP_FILE_INSTALL) --dir $(DESTDIR)/usr/share/applications $(srcdir)/wireshark.desktop; \
	else \
		install -m 644 $(srcdir)/wireshark.desktop $(DESTDIR)/usr/share/applications/wireshark.desktop; \
	fi
	for size in 16 24 32 48 64 128 256; \
	do \
		mkdir -p $(DESTDIR)/usr/share/icons/hicolor/$${size}x$${size}/{apps,mimetypes} ; \
		install -m 644 $(srcdir)/image/wsicon$${size}.png $(DESTDIR)/usr/share/icons/hicolor/$${size}x$${size}/apps/wireshark.png ; \
		install -m 644 $(srcdir)/image/WiresharkDoc-$${size}.png $(DESTDIR)/usr/share/icons/hicolor/$${size}x$${size}/mimetypes/application-wireshark-doc.png ; \
	done
	mkdir -p $(DESTDIR)/usr/share/icons/hicolor/scalable/apps
	install -m 644 image/wsicon.svg $(DESTDIR)/usr/share/icons/hicolor/scalable/apps/wireshark.svg
	@echo "Don't forget to run \"update-desktop-database\" and \"update-mime-database /usr/share/mime\""

# Used by svr4-package and osx-package
# We load top_stagedir with an explicit path so that libtool doesn't freak.
top_stagedir=`cd $(top_builddir) && pwd`/packaging/staging
stagedir=$(top_stagedir)/$(PACKAGE).inst

host_cpu=@host_cpu@
host_os=@host_os@

solaris-package: svr4-package

svr4-package: $(PROGRAMS) $(SCRIPTS) $(MANS) $(DATA)
	@if test x$(HAVE_SVR4_PACKAGING) = xyes ; then \
		rm -rf $(stagedir) ; \
		$(MAKE) DESTDIR=$(stagedir) install; \
		$(srcdir)/packaging/svr4/mkpkg \
			$(PACKAGE) \
			$(PACKAGE)-$(VERSION)-$(host_os)-$(host_cpu)-local \
			$(prefix) \
			$(top_stagedir) ; \
	else \
		echo "Error: SVR4 packaging tools not found." ; \
		echo "Package build abandoned." ; \
	fi


rpm_topdir=`cd $(top_builddir) && pwd`/packaging/rpm
rpm-package: dist
	@if test x$(HAVE_RPM) = xyes ; then \
		cd $(rpm_topdir) ; \
		mkdir -p BUILD RPMS SOURCES SRPMS; \
		cd SOURCES ; \
		ln -sf ../../../$(distdir).tar.bz2 ; \
		cd .. ; \
		rpmbuild --define "_topdir `cd . && pwd`" --define "_prefix $(prefix)" \
			@RPMBUILD_WITH_ARGS@ --clean -ba SPECS/wireshark.spec && \
			echo "Package successfully built in `pwd`/RPMS." && \
			rm -f SOURCES/$(distdir).tar.bz2 $(distdir).tar.bz2 ; \
	else \
		echo "Error: RPM executable and/or source directory not found." ; \
		false; \
	fi

debian-package: debian/rules
	@if test x$(HAVE_DPKG_BUILDPACKAGE) = xyes ; then \
		dpkg-buildpackage -rfakeroot -us -uc ; \
	else \
		echo "Error: Debian packaging tools not found." ; \
		echo "Package build abandoned." ; \
	fi

# XXX - This assumes we're building from the source directory.
osx-app: $(PROGRAMS) $(SCRIPTS) $(MANS) $(DATA) packaging/macosx/Info.plist
	@if test x$(HAVE_OSX_PACKAGING) = xyes ; then \
		rm -rf $(stagedir) ; \
		$(MAKE) DESTDIR=$(stagedir) install; \
		cd $(srcdir)/packaging/macosx ;  \
		./osx-app.sh @OSX_APP_FLAGS@ -bp ../staging/$(PACKAGE).inst$(bindir) ; \
	else \
		echo "Error: OS X packaging tools not found." ; \
		echo "Package build abandoned." ; \
	fi

packaging/macosx/COPYING.txt: COPYING
	(cd packaging/macosx ; \
	$(MAKE) COPYING.txt ;)

osx-package: osx-app packaging/macosx/COPYING.txt
	@if test x$(HAVE_OSX_PACKAGING) = xyes ; then \
		cd $(srcdir)/packaging/macosx ;  \
		chmod +x ./osx-dmg.sh ; \
		./osx-dmg.sh @OSX_DMG_FLAGS@ ; \
	fi

osx-install: osx-app
	@if test x$(HAVE_OSX_PACKAGING) = xyes ; then \
		echo "Copying Wireshark.app to /Applications" ; \
		cp -pr $(srcdir)/packaging/macosx/Wireshark.app /Applications ;  \
	fi

clean-local:
	rm -rf $(top_stagedir)

dumpabi:
	$(MAKE) -C filetap dumpabi-libfiletap
	$(MAKE) -C wiretap dumpabi-libwiretap
	$(MAKE) -C epan dumpabi-libwireshark
	$(MAKE) -C wsutil dumpabi-libwsutil

checkapi_local:
	$(PERL) $(top_srcdir)/tools/checkAPIs.pl -build \
	-sourcedir=$(srcdir) \
	$(TSHARK_TAP_SRC) \
	$(wireshark_SOURCES)
#	$(EXTRA_wireshark_SOURCES)

checkapi: checkapi_local
	cd wiretap && $(MAKE) checkapi
	cd filetap && $(MAKE) checkapi
	cd codecs && $(MAKE) checkapi
	cd ui && $(MAKE) checkapi
	cd ui/gtk && $(MAKE) checkapi
##	cd epan && $(MAKE) checkapi
##	cd epan/crypt && $(MAKE) checkapi
	cd epan/dfilter && $(MAKE) checkapi
##	cd epan/ftypes && $(MAKE) checkapi
##	cd epan/wslua && $(MAKE) checkapi
	cd epan/dissectors && $(MAKE) checkapi
	cd plugins && $(MAKE) checkapi
	cd wsutil && $(MAKE) checkapi

wsar_html: doxygen.cfg doxygen_global.cfg FORCE
if HAVE_DOXYGEN
	rm -rf wsar_html
	cd epan && $(MAKE) $@
	cd ui && $(MAKE) $@
	(umask 022 ; $(DOXYGEN) doxygen.cfg)
endif

wsar-zip: wsar_html
if HAVE_DOXYGEN
	rm -f wsar_html.zip
	zip -rq wsar_html.zip wsar_html
endif

