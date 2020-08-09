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

CMD ["java", "-jar", "/usr/lib/jenkins/jenkins.war", "start"]
EXPOSE 8080/tcp
