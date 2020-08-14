FROM ubuntu:focal

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
	&& apt-get install -y vim curl sudo

RUN useradd --user-group --create-home --shell /bin/bash foam ;\
	echo "foam ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

RUN curl -s https://dl.openfoam.com/add-debian-repo.sh | bash ;\
	apt-get install -y openfoam2006 openfoam2006-tutorials ;\
	rm -rf /var/lib/apt/lists/* ;\
	echo "source /usr/lib/openfoam/openfoam2006/etc/bashrc" >> ~foam/.bashrc ;\
	echo "export OMPI_MCA_btl_vader_single_copy_mechanism=none" >> ~foam/.bashrc

USER foam