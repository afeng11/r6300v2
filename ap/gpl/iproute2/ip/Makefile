include ../../config.in
include ../../config.mk

IPOBJ=ip.o ipaddress.o iproute.o iprule.o \
    rtm_map.o iptunnel.o ipneigh.o iplink.o \
    ipmaddr.o ipmonitor.o ipmroute.o ipprefix.o \
    ipxfrm.o xfrm_state.o xfrm_policy.o xfrm_monitor.o

RTMONOBJ=rtmon.o

ALLOBJ=$(IPOBJ) $(RTMONOBJ)
SCRIPTS=ifcfg rtpr routel routef

#TARGETS=ip rtmon
TARGETS=ip


all: $(TARGETS) $(SCRIPTS)

ip: $(IPOBJ) $(LIBNETLINK) $(LIBUTIL)

rtmon: $(RTMONOBJ) $(LIBNETLINK)

install: all
	install -m 0755 $(TARGETS) $(DESTDIR)$(SBINDIR)
	$(STRIP) $(DESTDIR)$(SBINDIR)/ip

#	$(STRIP) $(DESTDIR)$(SBINDIR)/rtmon
#	install -m 0755 $(SCRIPTS) $(DESTDIR)$(SBINDIR)


clean:
	rm -f $(ALLOBJ) $(TARGETS)

