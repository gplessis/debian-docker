build: squeeze-amd64.tar
	docker build -t dotdeb/debian:squeeze-amd64 ./

squeeze-amd64.tar: squeeze-amd64-chroot
	cd squeeze-amd64 && tar cf ../squeeze-amd64.tar ./

squeeze-amd64-chroot:
	mkdir -p squeeze-amd64
	debootstrap --arch amd64 squeeze ./squeeze-amd64 http://http.debian.net/debian
	chroot ./squeeze-amd64 apt-get clean

clean:
	rm -f squeeze-amd64.tar
	rm -r squeeze-amd64-chroot

.PHONY: squeeze-amd64-chroot clean
