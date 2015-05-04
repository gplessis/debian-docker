FROM scratch
MAINTAINER Guillaume Plessis "gui@dotdeb.org"

ENV DEBIAN_FRONTEND noninteractive

ADD jessie-amd64.tar /

RUN echo "deb http://http.debian.net/debian/ jessie main contrib non-free" > /etc/apt/sources.list
RUN echo "deb http://http.debian.net/debian/ jessie-updates main contrib non-free" >> /etc/apt/sources.list
RUN echo "deb http://http.debian.net/debian/ jessie-backports main contrib non-free" >> /etc/apt/sources.list
RUN echo "deb http://security.debian.org/ jessie/updates main contrib non-free" >> /etc/apt/sources.list

RUN echo "APT::Install-Recommends "false";" > /etc/apt/apt.conf.d/10recommends
RUN echo "APT::Install-Suggests "false";" >> /etc/apt/apt.conf.d/10recommends

RUN apt-get update \
	&& apt-get -y upgrade \
	&& apt-get -y autoremove \
	&& apt-get clean \
	&& find /var/lib/apt/lists -type f -delete
CMD ["/bin/bash"]
