SHELL=/bin/sh

CC=gcc
CFLAGS=
DESTDIR=
PREFIX=usr
BINDIR=bin
ETCDIR=etc
LIBDIR=lib
SBINDIR=sbin

SCRIPTS= 1 2 3 ctrlaltdel

all:
	${CC} ${CFLAGS} -v halt.c -o halt
	${CC} ${CFLAGS} -v pause.c -o pause

install:
	install -dv ${DESTDIR}/${ETCDIR}/sysconfig
	install -dv ${DESTDIR}/${LIBDIR}/services
	ln -sfv /${LIBDIR}/services /${LIBDIR}/lsb
	install -v -m 0755 halt ${DESTDIR}/${SBINDIR}
	install -v -m 0755 pause ${DESTDIR}/${PREFIX}/${BINDIR}
	install -v -m 0755 shutdown ${DESTDIR}/${SBINDIR}
	install -v -m 0755 ifup ${DESTDIR}/${SBINDIR}
	install -v -m 0755 ifdown ${DESTDIR}/${SBINDIR}
	install -v -m 0755 runlevel ${DESTDIR}/${SBINDIR}
	ln -svf halt ${DESTDIR}/${SBINDIR}/poweroff
	ln -svf halt ${DESTDIR}/${SBINDIR}/reboot
	install -dv ${DESTDIR}/${PREFIX}/share/man/man5
	install -dv ${DESTDIR}/${PREFIX}/share/man/man8
	install -v -m 0644 pause.8 ${DESTDIR}/${PREFIX}/share/man/man8
	install -v -m 0664 runit.conf.5 ${DESTDIR}/${PREFIX}/share/man/man5
	install -v -m 0644 shutdown.8 ${DESTDIR}/${PREFIX}/share/man/man8
	install -v -m 0644 halt.8 ${DESTDIR}/${PREFIX}/share/man/man8
	install -v -m 0644 ifup.8 ${DESTDIR}/${PREFIX}/share/man/man8
	install -v -m 0664 rc.local.5 ${DESTDIR}/${PREFIX}/share/man/man5
	install -v -m 0644 runlevel.8 ${DESTDIR}/${PREFIX}/share/man/man8
	ln -sfv ifup.8 ${DESTDIR}/${PREFIX}/share/man/man8/ifdown.8
	ln -sfv halt.8 ${DESTDIR}/${PREFIX}/share/man/man8/poweroff.8
	ln -sfv halt.8 ${DESTDIR}/${PREFIX}/share/man/man8/reboot.8
	install -v -m 0754 ipv4-static-route ${DESTDIR}/${LIBDIR}/services
	install -v -m 0754 ipv4-static ${DESTDIR}/${LIBDIR}/services
	install -dv ${DESTDIR}/${ETCDIR}/sv
	install -dv ${DESTDIR}/${ETCDIR}/runit/rc.d
	install -dv ${DESTDIR}/${ETCDIR}/runit/runsvdir/single
	install -dv ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	install -v -m 0755 ${SCRIPTS} ${DESTDIR}/${ETCDIR}/runit
	install -v -m 0644 runit.conf ${DESTDIR}/${ETCDIR}
	install -v -m 0755 rc.local ${DESTDIR}/${ETCDIR}
	cp -apv services/* ${DESTDIR}/${ETCDIR}/sv/
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/agetty-tty1 ${DESTDIR}/${ETCDIR}/runit/runsvdir/single
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/agetty-tty1 ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/agetty-tty2 ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/agetty-tty3 ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/agetty-tty4 ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/agetty-tty5 ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/agetty-tty6 ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	ln -sfv ${DESTDIR}/${ETCDIR}/sv/update-cache ${DESTDIR}/${ETCDIR}/runit/runsvdir/multi
	chmod +x ${DESTDIR}/${ETCDIR}/sv/agetty-tty1/*
	chmod +x ${DESTDIR}/${ETCDIR}/sv/agetty-tty2/*
	chmod +x ${DESTDIR}/${ETCDIR}/sv/agetty-tty3/*
	chmod +x ${DESTDIR}/${ETCDIR}/sv/agetty-tty4/*
	chmod +x ${DESTDIR}/${ETCDIR}/sv/agetty-tty5/*
	chmod +x ${DESTDIR}/${ETCDIR}/sv/agetty-tty6/*
	chmod +x ${DESTDIR}/${ETCDIR}/sv/update-cache/*
	install -dv ${DESTDIR}/${PREFIX}/share/doc/runit-for-lfs
	install -v -m 0644 ../CHANGELOG ${DESTDIR}/${PREFIX}/share/doc/runit-for-lfs
	install -v -m 0644 ../INSTALL ${DESTDIR}/${PREFIX}/share/doc/runit-for-lfs
	install -v -m 0644 ../LICENSE-MIT ${DESTDIR}/${PREFIX}/share/doc/runit-for-lfs
	install -v -m 0644 ../README ${DESTDIR}/${PREFIX}/share/doc/runit-for-lfs
	install -v -m 0644 ../Release_Notes ${DESTDIR}/${PREFIX}/share/doc/runit-for-lfs

clean:
	-rm -vf halt pause suspend

uninstall:
	$(info WARNING!!! CAUTION!!! STOP!!! CEASE!!!)
	$(info)
	$(info Uninstallation outside of chroot is not advised!!!)
	$(info Please use chroot from a host to use the uninstall)
	$(info or you may be left with a non-operable system!!!)
	$(info)
	$(info Please enter chroot first and run make uninstall-true.)

uninstall-true:
	-rm -rvf ${DESTDIR}/${ETCDIR}/runit.conf
	-rm -rvf ${DESTDIR}/${ETCDIR}/sv
	-rm -rvf ${DESTDIR}/${ETCDIR}/runit
	-rm -rvf ${DESTDIR}/${ETCDIR}/rc.local
	-rm -rvf ${DESTDIR}/${SBINDIR}/poweroff
	-rm -rvf ${DESTDIR}/${SBINDIR}/reboot
	-rm -rvf ${DESTDIR}/${SBINDIR}/suspend
	-rm -rvf ${DESTDIR}/${SBINDIR}/shutdown
	-rm -rvf ${DESTDIR}/${SBINDIR}/halt
	-rm -rvf ${DESTDIR}/${SBINDIR}/ifup
	-rm -rvf ${DESTDIR}/${SBINDIR}/ifdown
	-rm -rvf ${DESTDIR}/${SBINDIR}/runlevel
	-rm -rvf ${DESTDIR}/${LIBDIR}/services/ipv4-static-route
	-rm -rvf ${DESTDIR}/${LIBDIR}/services/ipv4-static
	-rm -rvf ${DESTDIR}/${PREFIX}/${BINDIR}/pause
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/ifdown.8
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/ifup.8
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/halt.8      
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/poweroff.8
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/reboot.8
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/shutdown.8
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man5/runit.conf.5
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/pause.8
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man5/rc.local.5
	-rm -rvf ${DESTDIR}/${PREFIX}/share/man/man8/runlevel.8
	-rm -rvf ${DESTDIR}/${PREFIX}/share/doc/runit-for-lfs

.PHONY : all install clean uninstall uninstall-true