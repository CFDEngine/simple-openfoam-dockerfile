FROM ubuntu:focal

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
	&& apt-get install -y \
		vim \
		ssh \
		sudo \
		wget \
		software-properties-common ;\
		rm -rf /var/lib/apt/lists/*

RUN useradd --user-group --create-home --shell /bin/bash foam ;\
	echo "foam ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

RUN sh -c "wget -O - http://dl.openfoam.org/gpg.key | apt-key add -" ;\
	add-apt-repository http://dl.openfoam.org/ubuntu ;\
	apt-get update ;\
	apt-get install -y openfoam8 paraviewopenfoam56- ;\
	rm -rf /var/lib/apt/lists/* ;\
	echo "source /opt/openfoam8/etc/bashrc" >> ~foam/.bashrc ;\
	echo "export OMPI_MCA_btl_vader_single_copy_mechanism=none" >> ~foam/.bashrc

USER foam