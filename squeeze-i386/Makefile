build: squeeze-i386.tar
	docker build -t dotdeb/debian:squeeze-i386 ./

squeeze-i386.tar: squeeze-i386-chroot
	cd squeeze-i386 && tar cf ../squeeze-i386.tar ./

squeeze-i386-chroot:
	mkdir -p squeeze-i386
	debootstrap --arch i386 squeeze ./squeeze-i386 http://http.debian.net/debian
	chroot ./squeeze-i386 apt-get clean

clean:
	rm -f squeeze-i386.tar
	rm -r squeeze-i386-chroot

.PHONY: squeeze-i386-chroot clean
