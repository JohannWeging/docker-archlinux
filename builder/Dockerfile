FROM base/archlinux:latest
MAINTAINER "Johann Weging <johann@weging.com>"


RUN set -x \
&& pacman --noconfirm -Syy \
&& pacman --noconfirm -S curl openssl reflector \
&& curl -o /etc/pacman.d/mirrorlist https://www.archlinux.org/mirrorlist/all/ \
&& reflector --verbose -l 5 --sort rate --save /etc/pacman.d/mirrorlist \
&& pacman --noconfirm -S pacman archlinux-keyring \
&& pacman-db-upgrade \
&& pacman --noconfirm -Suy \
&& pacman --noconfirm -S expect arch-install-scripts

ADD mkimage-arch.sh /
ADD mkimage-arch-pacman.conf /
