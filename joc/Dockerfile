FROM java:8
MAINTAINER EricoGR <ericogr@gmail.com>

#JOC Jobscheduler download URL
ENV JOC_JS_URL https://download.sos-berlin.com/JobScheduler.1.11/joc_linux.1.11.1.tar.gz

#download and install joc job scheduler
RUN curl -o /root/joc_linux.tar.gz $JOC_JS_URL
RUN mkdir /root/install && tar xzvf /root/joc_linux.tar.gz -C /root/install --strip-components=1
COPY joc_install.xml /root/install/joc_install.xml
COPY startup_joc.sh /opt/startup_joc.sh

#expose scheduler ports
EXPOSE 40444 48444 4444

#start wrapper script
CMD chmod +x /opt/startup_joc.sh
CMD ["bash","/opt/startup_joc.sh"]
