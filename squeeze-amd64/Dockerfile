FROM scratch
MAINTAINER Guillaume Plessis "gui@dotdeb.org"

ENV DEBIAN_FRONTEND noninteractive

ADD squeeze-amd64.tar /

RUN echo "deb http://http.debian.net/debian/ squeeze main contrib non-free" > /etc/apt/sources.list \
	&& echo "deb http://http.debian.net/debian/ squeeze-updates main contrib non-free" >> /etc/apt/sources.list \
	&& echo "deb http://http.debian.net/debian/ squeeze-lts main contrib non-free" >> /etc/apt/sources.list \
	&& echo "deb http://security.debian.org/ squeeze/updates main contrib non-free" >> /etc/apt/sources.list \
	&& echo "deb http://backports.debian.org/debian-backports squeeze-backports main contrib non-free" >> /etc/apt/sources.list \
	&& echo "APT::Install-Recommends "false";" > /etc/apt/apt.conf.d/10recommends \
	&& echo "APT::Install-Suggests "false";" >> /etc/apt/apt.conf.d/10recommends \
	&& apt-get update \
	&& apt-get -y upgrade \
	&& apt-get -y autoremove \
	&& apt-get clean \
	&& find /var/lib/apt/lists -type f -delete

CMD ["/bin/bash"]
