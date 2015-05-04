build: wheezy-amd64.tar
	docker build -t dotdeb/debian:wheezy-amd64 ./

wheezy-amd64.tar: wheezy-amd64-chroot
	cd wheezy-amd64 && tar cf ../wheezy-amd64.tar ./

wheezy-amd64-chroot:
	mkdir -p wheezy-amd64
	debootstrap --arch amd64 wheezy ./wheezy-amd64 http://http.debian.net/debian
	chroot ./wheezy-amd64 apt-get clean

clean:
	rm -f wheezy-amd64.tar
	rm -r wheezy-amd64-chroot

.PHONY: wheezy-amd64-chroot clean
