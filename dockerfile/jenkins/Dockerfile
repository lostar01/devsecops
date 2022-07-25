FROM docker.io/centos:7.6.1810

RUN useradd -u 1000  jenkins && \
    gpasswd -a jenkins root && \
    yum install -y java-11-openjdk-devel git  && \
    mkdir -p /var/jenkins_home && \
    mkdir -p /usr/share/jenkins/ref && \
    chown -R jenkins:jenkins /var/jenkins_home /usr/share/jenkins/ref

USER jenkins

COPY file/tini-sbin /sbin/tini
COPY file/tini /bin/tini
COPY file/jenkins.sh /usr/local/bin/jenkins.sh
COPY file/jenkins.war /usr/share/jenkins/jenkins.war

ENV PATH "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV LANG "C.UTF-8"
ENV JENKINS_HOME "/var/jenkins_home"
ENV JENKINS_SLAVE_AGENT_PORT "50000"
ENV TINI_VERSION "0.14.0"
ENV TINI_SHA "6c41ec7d33e857d4779f14d9c74924cab0c7973485d2972419a3b7c7620ff5fd"
ENV JENKINS_VERSION "2.60.3"
ENV JENKINS_UC "https://updates.jenkins.io"
ENV JENKINS_UC_EXPERIMENTAL "https://updates.jenkins.io/experimental",
ENV COPY_REFERENCE_FILE_LOG "/var/jenkins_home/copy_reference_file.log"

EXPOSE 8080
EXPOSE 50000

ENTRYPOINT [ "/bin/tini","--","/usr/local/bin/jenkins.sh"]
