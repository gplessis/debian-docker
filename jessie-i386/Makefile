build: jessie-i386.tar
	docker build -t gplessis/debian:jessie-i386 ./

jessie-i386.tar: jessie-i386-chroot
	cd jessie-i386 && tar cf ../jessie-i386.tar ./

jessie-i386-chroot:
	mkdir -p jessie-i386
	debootstrap --arch i386 jessie ./jessie-i386 http://http.debian.net/debian
	chroot ./jessie-i386 apt-get clean

clean:
	rm -f jessie-i386.tar
	rm -r jessie-i386-chroot

.PHONY: jessie-i386-chroot clean
