build: jessie-amd64.tar
	docker build -t gplessis/debian:jessie-amd64 ./

jessie-amd64.tar: jessie-amd64-chroot
	cd jessie-amd64 && tar cf ../jessie-amd64.tar ./

jessie-amd64-chroot:
	mkdir -p jessie-amd64
	debootstrap --arch amd64 jessie ./jessie-amd64 http://http.debian.net/debian
	chroot ./jessie-amd64 apt-get clean

clean:
	rm -f jessie-amd64.tar
	rm -r jessie-amd64-chroot

.PHONY: jessie-amd64-chroot clean
