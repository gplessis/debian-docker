build: wheezy-i386.tar
	docker build -t dotdeb/debian:wheezy-i386 ./

wheezy-i386.tar: wheezy-i386-chroot
	cd wheezy-i386 && tar cf ../wheezy-i386.tar ./

wheezy-i386-chroot:
	mkdir -p wheezy-i386
	debootstrap --arch i386 wheezy ./wheezy-i386 http://http.debian.net/debian
	chroot ./wheezy-i386 apt-get clean

clean:
	rm -f wheezy-i386.tar
	rm -r wheezy-i386-chroot

.PHONY: wheezy-i386-chroot clean
