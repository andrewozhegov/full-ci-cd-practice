FROM amazonlinux:2

RUN yum -y install java-1.8.0-openjdk

RUN yum -y install wget
RUN wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
RUN rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
RUN yum -y install jenkins

RUN yum install -y yum-utils
RUN yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
RUN yum -y install docker-ce-cli

RUN yum -y install git tar

RUN wget http://apachemirror.wuchna.com/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz && \
    tar -xvzf apache-maven-3.6.3-bin.tar.gz && rm -f apache-maven-3.6.3-bin.tar.gz

ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.252.b09-2.amzn2.0.1.x86_64/jre
ENV M2_HOME=/apache-maven-3.6.3
ENV PATH="$JAVA_HOME/bin:$M2_HOME/bin:${PATH}"

CMD ["java", "-jar", "/usr/lib/jenkins/jenkins.war", "start"]
EXPOSE 8080/tcp
