FROM jboss/wildfly:20.0.1.Final

RUN /opt/jboss/wildfly/bin/add-user.sh speedlog speedlog --silent
COPY pl /opt/jboss/wildfly/modules/pl
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]