FROM jenkins/jenkins

USER root
RUN apt-get -y update && \
	apt-get -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common && \
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - && \
 	add-apt-repository \
 	"deb [arch=amd64] https://download.docker.com/linux/debian \
 	$(lsb_release -cs) \
 	stable" && \
 	apt-get update && \
 	apt-get -y install docker-ce docker-ce-cli containerd.io sudo
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
RUN curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
	chmod +x /usr/local/bin/docker-compose && \
	ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
USER jenkins
#COPY plugins.txt /usr/local/bin/plugins.txt
#RUN /usr/local/bin/install-plugins.sh plugins.txt

#RUN apt-get update && apt-get install -y docker.io && rm -rf /var/lib/apt/lists/*
#RUN echo "deb http://apt.dockerproject.org/repo debian-jessie main" \
#	> /etc/apt/sources.list.d/docker.list \
#	&& apt-key adv --keyserver hkp://p80.pool.sks-keyserver.net:80 \
#		--recv-keys 58118E89F3A912897C070ADBF76221572C52609D \
#	&& apt-get update \
#	&& apt-get install -y apt-transport-https \
#	&& apt-get install -y sudo \
#	&& apt-get install -y docker-engine \
#	&& rm -rf /var/lib/apt/lists/*
#RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
#USER jenkins


