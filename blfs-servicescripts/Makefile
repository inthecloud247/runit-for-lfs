SHELL=/bin/bash

ETCDIR=/etc
LIBDIR=${DESTDIR}/lib/services
EXTDIR=${DESTDIR}${ETCDIR}
MODE=754
DIRMODE=755
CONFMODE=644

all:
	@grep "^install" Makefile | cut -d ":" -f 1
	@echo "Select an appropriate install target from the above list" 

create-dirs:
	install -d -m ${DIRMODE} ${EXTDIR}/sysconfig

create-service-dir:
	install -d -m ${DIRMODE} ${LIBDIR}

install-service-dhclient: create-service-dir
	install -m ${MODE} lsb/dhclient ${LIBDIR}

install-service-dhcpcd: create-service-dir
	install -m ${MODE} lsb/dhcpcd  ${LIBDIR}

install-service-bridge: create-service-dir
	install -m ${MODE} lsb/bridge  ${LIBDIR}

install-service-wpa: create-service-dir
	install -m ${MODE} lsb/wpa ${LIBDIR}

install-acpid:
	mkdir -pv ${ETCDIR}/sv/acpid
	cp -apv services/acpid/* ${EXTDIR}/sv/acpid
	ln -sfv ${EXTDIR}/sv/acpid ${EXTDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/acpid/*
	chmod +x ${ETCDIR}/sv/acpid/log/*

install-alsa:
	mkdir -pv ${ETCDIR}/sv/audio
	cp -apv services/audio/* ${ETCDIR}/sv/audio
	ln -sfv ${EXTDIR}/sv/audio ${EXTDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/audio/*

install-autofs:
	install -m ${CONFMODE} sysconfig/autofs.conf ${EXTDIR}/sysconfig/
	mkdir -pv ${ETCDIR}/sv/autofs
	cp -apv services/autofs/* ${ETCDIR}/sv/autofs
	ln -sfv ${EXTDIR}/sv/autofs ${EXTDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/autofs/*

install-atd:
	mkdir -pv ${ETCDIR}/sv/atd
	cp -apv services/atd/* ${ETCDIR}/sv/atd
	ln -sfv ${EXTDIR}/sv/atd ${EXTDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/atd/*
	chmod +x ${ETCDIR}/sv/atd/log/*

install-avahi:
	mkdir -pv ${ETCDIR}/sv/avahi-daemon
	cp -apv services/avahi-daemon/* ${ETCDIR}/sv/avahi-daemon
	ln -sfv ${ETCDIR}/sv/avahi-daemon ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/avahi-daemon/*

install-bind:
	mkdir -pv ${ETCDIR}/sv/bind
	cp -apv services/bind/* ${ETCDIR}/sv/bind
	ln -sfv ${ETCDIR}/sv/bind ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/bind/*

install-bluetooth: create-dirs
	install -m ${CONFMODE} sysconfig/bluetooth ${EXTDIR}/sysconfig/bluetooth
	mkdir -pv ${ETCDIR}/sv/bluetooth
	cp -apv services/bluetooth/* ${ETCDIR}/sv/bluetooth
	ln -sfv ${ETCDIR}/sv/bluetooth ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/bluetooth/*
	chmod +x ${ETCDIR}/sv/bluetooth/log/*

install-cups:
	mkdir -pv ${ETCDIR}/sv/cupsd
	cp -apv services/cupsd/* ${ETCDIR}/sv/cupsd
	ln -sfv ${ETCDIR}/sv/cupsd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/cupsd/*

install-dbus:
	mkdir -pv ${ETCDIR}/sv/dbus
	cp -apv services/dbus/* ${ETCDIR}/sv/dbus
	ln -sfv ${ETCDIR}/sv/dbus ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/dbus/*
	chmod +x ${ETCDIR}/sv/dbus/log/*

install-dhcpd: create-dirs
	install -m ${CONFMODE} sysconfig/dhcpd ${EXTDIR}/sysconfig/dhcpd
	mkdir -pv ${ETCDIR}/sv/dhcpd
	cp -apv services/dhcpd/* ${ETCDIR}/sv/dhcpd
	ln -sfv ${ETCDIR}/sv/dhcpd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/dhcpd/*
	chmod +x ${ETCDIR}/sv/dhcpd/log/*

install-dovecot:
	mkdir -pv ${ETCDIR}/sv/dovecot
	cp -apv services/dovecot/* ${ETCDIR}/sv/dovecot
	ln -sfv ${ETCDIR}/sv/dovecot ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/dovecot/*

install-exim:
	mkdir -pv ${ETCDIR}/sv/exim
	cp -apv services/exim/* ${ETCDIR}/sv/exim
	ln -sfv ${ETCDIR}/sv/exim ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/exim/*

install-fcron:
	mkdir -pv ${ETCDIR}/sv/fcron
	cp -apv services/fcron/* ${ETCDIR}/sv/fcron
	ln -sfv ${ETCDIR}/sv/fcron ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/fcron/*
	chmod +x ${ETCDIR}/sv/fcron/log/*

install-gpm:
	mkdir -pv ${ETCDIR}/sv/gpm
	cp -apv services/gpm/* ${ETCDIR}/sv/gpm
	ln -sfv ${ETCDIR}/sv/gpm ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/gpm/*

install-haveged:
	mkdir -pv ${ETCDIR}/sv/haveged
	cp -apv services/haveged/* ${ETCDIR}/sv/haveged
	ln -sfv ${ETCDIR}/sv/haveged ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/haveged/*

install-httpd:
	mkdir -pv ${ETCDIR}/sv/httpd
	cp -apv services/httpd/* ${ETCDIR}/sv/httpd
	ln -sfv ${ETCDIR}/sv/httpd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/httpd/*

install-iptables:
	mkdir -pv ${ETCDIR}/sv/iptables
	cp -apv services/iptables/* ${ETCDIR}/sv/iptables
	ln -sfv ${ETCDIR}/sv/iptables ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/iptables/*

install-kdm:
	mkdir -pv ${ETCDIR}/sv/kdm
	cp -apv services/kdm/* ${ETCDIR}/sv/kdm
	ln -sfv ${ETCDIR}/sv/kdm ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/kdm/*
	chmod +x ${ETCDIR}/sv/kdm/log/*

install-krb5:
	mkdir -pv ${ETCDIR}/sv/krb5
	cp -apv services/krb5/* ${ETCDIR}/sv/krb5
	ln -sfv ${ETCDIR}/sv/krb5 ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/krb5/*

install-lxdm:
	mkdir -pv ${ETCDIR}/sv/lxdm
	cp -apv services/lxdm/* ${ETCDIR}/sv/lxdm
	ln -sfv ${ETCDIR}/sv/lxdm ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/lxdm/*

install-mysql:
	mkdir -pv ${ETCDIR}/sv/mysql
	cp -apv services/mysql/* ${ETCDIR}/sv/mysql
	ln -sfv ${ETCDIR}/sv/mysql ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/mysql/*

install-netfs:
	mkdir -pv ${ETCDIR}/sv/netfs
	cp -apv services/netfs/* ${ETCDIR}/sv/netfs
	ln -sfv ${ETCDIR}/sv/netfs ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/netfs/*

install-networkmanager:
	mkdir -pv ${ETCDIR}/sv/networkmanager
	cp -apv services/networkmanager/* ${ETCDIR}/sv/networkmanager
	ln -sfv ${ETCDIR}/sv/networkmanager ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/networkmanager/*

install-nfs-client:
	mkdir -pv ${ETCDIR}/sv/nfs-client
	cp -apv services/nfs-client/* ${ETCDIR}/sv/nfs-client
	ln -sfv ${ETCDIR}/sv/nfs-client ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/nfs-client/*

install-nfs-server:
	mkdir -pv ${ETCDIR}/sv/nfs-server
	cp -apv services/nfs-server/* ${ETCDIR}/sv/nfs-server
	ln -sfv ${ETCDIR}/sv/nfs-server ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/nfs-server/*

install-ntpd:
	mkdir -pv ${ETCDIR}/sv/ntpd
	cp -apv services/ntpd/* ${ETCDIR}/sv/ntpd
	ln -sfv ${ETCDIR}/sv/ntpd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/ntpd/*
	chmod +x ${ETCDIR}/sv/ntpd/log/*

install-php:
	mkdir -pv ${ETCDIR}/sv/php-fpm
	cp -apv services/php-fpm/* ${ETCDIR}/sv/php-fpm
	ln -sfv ${ETCDIR}/sv/php-fpm ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/php-fpm/*

install-postfix:
	mkdir -pv ${ETCDIR}/sv/postfix
	cp -apv services/postfix/* ${ETCDIR}/sv/postfix
	ln -sfv ${ETCDIR}/sv/postfix ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/postfix/*

install-postgresql:
	mkdir -pv ${ETCDIR}/sv/postgresql
	cp -apv services/postgresql/* ${ETCDIR}/sv/postgresql
	ln -sfv ${ETCDIR}/sv/postgresql ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/postgresql/*
	chmod +x ${ETCDIR}/sv/postgresql/log/*

install-proftpd:
	mkdir -pv ${ETCDIR}/sv/proftpd
	cp -apv services/proftpd/* ${ETCDIR}/sv/proftpd
	ln -sfv ${ETCDIR}/sv/proftpd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/proftpd/*

install-qpopper:
	mkdir -pv ${ETCDIR}/sv/qpopper
	mkdir -pv ${ETCDIR}/sv/qpopper-ssl
	cp -apv services/qpopper/* ${ETCDIR}/sv/qpopper
	cp -apv services/qpopper-ssl/* ${ETCDIR}/sv/qpopper-ssl
	ln -sfv ${ETCDIR}/sv/qpopper ${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${ETCDIR}/sv/qpopper-ssl ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/qpopper/*
	chmod +x ${ETCDIR}/sv/qpopper-ssl/*
	chmod +x ${ETCDIR}/sv/qpopper/log/*
	chmod +x ${ETCDIR}/sv/qpopper-ssl/log/*

install-rpcbind:
	mkdir -pv ${ETCDIR}/sv/rpcbind
	cp -apv services/rpcbind/* ${ETCDIR}/sv/rpcbind
	ln -sfv ${ETCDIR}/sv/rpcbind ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/rpcbind/*

install-rsyncd:
	mkdir -pv ${ETCDIR}/sv/rsyncd
	cp -apv services/rsyncd/* ${ETCDIR}/sv/rsyncd
	ln -sfv ${ETCDIR}/sv/rsyncd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/rsyncd/*
	chmod +x ${ETCDIR}/sv/rsyncd/log/*

install-samba:
	mkdir -pv ${ETCDIR}/sv/nmbd
	mkdir -pv ${ETCDIR}/sv/smbd
	cp -apv services/nmbd/* ${ETCDIR}/sv/nmbd
	cp -apv services/smbd/* ${ETCDIR}/sv/smbd
	ln -sfv ${ETCDIR}/sv/nmbd ${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${ETCDIR}/sv/smbd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/nmbd/*
	chmod +x ${ETCDIR}/sv/smbd/*
	chmod +x ${ETCDIR}/sv/nmbd/log/*
	chmod +x ${ETCDIR}/sv/smbd/log/*

install-saslauthd:
	mkdir -pv ${ETCDIR}/sv/saslauthd
	cp -apv services/saslauthd/* ${ETCDIR}/sv/saslauthd
	ln -sfv ${ETCDIR}/sv/saslauthd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/saslauthd/*

install-sendmail:
	mkdir -pv ${ETCDIR}/sv/sendmail
	cp -apv services/sendmail/* ${ETCDIR}/sv/sendmail
	ln -sfv ${ETCDIR}/sv/sendmail ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/sendmail/*

install-slapd:
	mkdir -pv ${ETCDIR}/sv/slapd
	cp -apv services/slapd/* ${ETCDIR}/sv/slapd
	ln -sfv ${ETCDIR}/sv/slapd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/slapd/*

install-smartd:
	mkdir -pv ${ETCDIR}/sv/smartd
	cp -apv services/smartd/* ${ETCDIR}/sv/smartd
	ln -sfv ${ETCDIR}/sv/smartd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/smartd/*
	chmod +x ${ETCDIR}/sv/smartd/log/*

install-soprano:
	mkdir -pv ${ETCDIR}/sv/soprano
	cp -apv services/soprano/* ${ETCDIR}/sv/soprano
	ln -sfv ${ETCDIR}/sv/soprano ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/soprano/*

install-sshd:
	mkdir -pv ${ETCDIR}/sv/sshd
	cp -apv services/sshd/* ${ETCDIR}/sv/sshd
	ln -sfv ${ETCDIR}/sv/sshd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/sshd/*
	chmod +x ${ETCDIR}/sv/sshd/log/*

install-stunnel:
	mkdir -pv ${ETCDIR}/sv/stunnel
	cp -apv services/stunnel/* ${ETCDIR}/sv/stunnel
	ln -sfv ${ETCDIR}/sv/stunnel ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/stunnel/*

install-svn:
	mkdir -pv ${ETCDIR}/sv/svn
	cp -apv services/svn/* ${ETCDIR}/sv/svn
	ln -sfv ${ETCDIR}/sv/svn ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/svn/*
	chmod +x ${ETCDIR}/sv/svn/log/*

install-swat:
	mkdir -pv ${ETCDIR}/sv/swat
	cp -apv services/swat/* ${ETCDIR}/sv/swat
	ln -sfv ${ETCDIR}/sv/swat ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/swat/*

install-sysstat:
	mkdir -pv ${ETCDIR}/sv/sysstat
	cp -apv services/sysstat/* ${ETCDIR}/sv/systat
	ln -sfv ${ETCDIR}/sv/sysstat ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/sysstat/*

install-unbound:
	mkdir -pv ${ETCDIR}/sv/unbound
	cp -apv services/unbound/* ${ETCDIR}/sv/unbound
	ln -sfv ${ETCDIR}/sv/unbound ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/unbound/*

install-vboxservice:
	mkdir -pv ${ETCDIR}/sv/vboxservice
	cp -apv services/vboxservice/* ${ETCDIR}/sv/vboxservice
	ln -sfv ${ETCDIR}/sv/vboxservice ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/vboxservice/*

install-virtuoso:
	mkdir -pv ${ETCDIR}/sv/virtuoso
	cp -apv services/virtuoso/* ${ETCDIR}/sv/virtuoso
	ln -sfv ${ETCDIR}/sv/virtuoso ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/virtuoso/*
	chmod +x ${ETCDIR}/sv/virtuoso/log/*

install-vsftpd:
	mkdir -pv ${ETCDIR}/sv/vsftpd
	cp -apv services/vsftpd/* ${ETCDIR}/sv/vsftpd
	ln -sfv ${ETCDIR}/sv/vsftpd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/vsftpd/*
	chmod +x ${ETCDIR}/sv/vsftpd/log/*

install-wicd:
	mkdir -pv ${ETCDIR}/sv/wicd
	cp -apv services/wicd/* ${ETCDIR}/sv/wicd
	ln -sfv ${ETCDIR}/sv/wicd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/wicd/*

install-winbindd:
	mkdir -pv ${ETCDIR}/sv/winbindd
	cp -apv services/winbindd/* ${ETCDIR}/sv/winbindd
	ln -sfv ${ETCDIR}/sv/winbindd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/winbindd/*

install-xinetd:
	mkdir -pv ${ETCDIR}/sv/xinetd
	cp -apv services/xinetd/* ${ETCDIR}/sv/xinetd
	ln -sfv ${ETCDIR}/sv/xinetd ${ETCDIR}/runit/runsvdir/multi
	chmod +x ${ETCDIR}/sv/xinetd/*

uninstall-acpid:
	rm -rvf ${ETCDIR}/sv/acpid

uninstall-alsa:
	rm -rvf ${ETCDIR}/sv/audio

uninstall-atd:
	rm -rvf ${ETCDIR}/sv/atd

uninstall-autofs:
	rm -vf ${ETCDIR}/sysconfig/autofs.conf
	rm -rvf ${ETCDIR}/sv/autofs

uninstall-avahi:
	rm -rvf ${ETCDIR}/sv/avahi-daemon

uninstall-bind:
	rm -rvf ${ETCDIR}/sv/bind

uninstall-bluetooth:
	rm -vf ${EXTDIR}/sysconfig/bluetooth
	rm -rfv ${ETCDIR}/sv/bluetooth

uninstall-cups:
	rm -rvf ${ETCDIR}/sv/cupsd

uninstall-dbus:
	rm -rvf ${ETCDIR}/sv/dbus

uninstall-dhcpd:
	rm -vf ${EXTDIR}/sysconfig/dhcpd
	rm -rvf ${ETCDIR}/sv/dhcpd

uninstall-dovecot:
	rm -rvf ${ETCDIR}/sv/dovecot

uninstall-exim:
	rm -rvf ${ETCDIR}/sv/exim

uninstall-fcron:
	rm -rvf ${ETCDIR}/sv/fcron

uninstall-gpm:
	rm -rvf ${ETCDIR}/sv/gpm

uninstall-haveged:
	rm -rvf ${ETCDIR}/sv/haveged

uninstall-httpd:
	rm -rvf ${ETCDIR}/sv/httpd

uninstall-iptables:
	rm -rvf ${ETCDIR}/sv/iptables

uninstall-kdm:
	rm -rvf ${ETCDIR}/sv/kdm

uninstall-krb5:
	rm -rvf ${ETCDIR}/sv/krb5

uninstall-mysql:
	rm -rvf ${ETCDIR}/sv/mysql

uninstall-netfs:
	rm -rvf ${ETCDIR}/sv/netfs

uninstall-networkmanager:
	rm -rvf ${ETCDIR}/sv/networkmanager

uninstall-nfs-client:
	rm -rvf ${ETCDIR}/sv/nfs-client

uninstall-nfs-server:
	rm -rvf ${ETCDIR}/sv/nfs-server

uninstall-ntpd:
	rm -rvf ${ETCDIR}/sv/ntpd

uninstall-php:
	rm -rvf ${ETCDIR}/sv/php-fpm

uninstall-postfix:
	rm -rvf ${ETCDIR}/sv/postfix

uninstall-postgresql:
	rm -rvf ${ETCDIR}/sv/postgresql

uninstall-proftpd:
	rm -rvf ${ETCDIR}/sv/proftpd

uninstall-qpopper:
	rm -rvf ${ETCDIR}/sv/qpopper
	rm -rvf ${ETCDIR}/sv/qpopper-ssl

uninstall-rsyncd:
	rm -rvf ${ETCDIR}/sv/rsyncd

uninstall-samba:
	rm -rvf ${ETCDIR}/sv/nmbd
	rm -rvf ${ETCDIR}/sv/smbd

uninstall-saslauthd:
	rm -f ${EXTDIR}/sysconfig/saslauthd
	rm -rvf ${ETCDIR}/sv/saslauthd

uninstall-sendmail:
	rm -rvf ${ETCDIR}/sv/sendmail

uninstall-slapd:
	rm -f ${EXTDIR}/sysconfig/slapd
	rm -rvf ${ETCDIR}/sv/slapd

uninstall-smartd:
	rm -rvf ${ETCDIR}/sv/smartd

uninstall-sshd:
	rm -rvf ${ETCDIR}/sv/sshd

uninstall-stunnel:
	rm -rvf ${ETCDIR}/sv/stunnel

uninstall-svn:
	rm -rvf ${ETCDIR}/sv/svn

uninstall-sysstat:
	rm -rvf ${ETCDIR}/sv/sysstat

uninstall-unbound:
	rm -rvf ${ETCDIR}/sv/unbound

uninstall-vboxservice:
	rm -rvf ${ETCDIR}/sv/vboxservice

uninstall-virtuoso:
	rm -rvf ${ETCDIR}/sv/virtuoso

uninstall-vsftpd:
	rm -rvf ${ETCDIR}/sv/vsftpd

uninstall-winbindd:
	rm -rvf ${ETCDIR}/sv/winbindd

uninstall-xinetd:
	rm -rvf ${ETCDIR}/sv/xinetd

.PHONY: all create-dirs create-service-dir \
	install-service-dhclient \
	install-service-dhcpcd \
	install-service-ipx \
	install-service-pppoe \
	install-atd \
	install-acpid \
	install-alsa \
	install-avahi \
	install-httpd \
	install-php \
	install-bind \
	install-bluetooth \
	install-cups \
	install-saslauthd \
	install-dhcpd \
	install-dovecot \
	install-exim \
	install-fcron \
	install-gdm \
	install-gpm \
	install-heimdal \
	install-iptables \
	install-kdm \
	install-krb5 \
	install-lxdm \
	install-mysql \
	install-netfs \
	install-networkmanager \
	install-nfs-client \
	install-nfs-server \
	install-ntp \
	install-slapd \
	install-postfix \
	install-postgresql \
	install-proftpd \
	install-qpopper \
	install-random \
	install-rsync \
	install-samba \
	install-sendmail \
	install-smartd \
	install-soprano \
	install-sshd \
	install-stunnel \
	install-svn \
	install-sysstat \
	install-vsftpd \
	install-unbound \
	install-vboxservice \
	install-virtuoso \
	install-winbindd \
	install-xinetd \
	uninstall-acpid \
	uninstall-alsa \
	uninstall-atd \
	uninstall-avahi \
	uninstall-bind \
	uninstall-bluetooth \
	uninstall-cups \
	uninstall-dhcpd \
	uninstall-dovecot \
	uninstall-exim \
	uninstall-fcron \
	uninstall-gpm \
	uninstall-httpd \
	uninstall-iptables \
	uninstall-kdm \
	uninstall-krb5 \
	uninstall-lxdm \
	uninstall-mysql \
	uninstall-netfs \
	uninstall-networkmanager \
	uninstall-nfs-client \
	uninstall-nfs-server \
	uninstall-ntp \
	uninstall-slapd \
	uninstall-php \
	uninstall-postfix \
	uninstall-postgresql \
	uninstall-proftpd \
	uninstall-qpopper \
	uninstall-rsync \
	uninstall-samba \
	uninstall-saslauthd \
	uninstall-sendmail \
	uninstall-smartd \
	uninstall-soprano \
	uninstall-sshd \
	uninstall-stunnel \
	uninstall-svn \
	uninstall-sysstat \
	uninstall-unbound \
	uninstall-vboxservice \
	uninstall-virtuoso \
	uninstall-vsftpd   \
	uninstall-winbindd \
	uninstall-xinetd
