FROM jasonrivers/nagios

RUN apt-get update && apt-get install nagios-plugins-basic -y

ADD ./etc/nagios/ /opt/nagios/etc/conf.d/

RUN chown -R nagios:nagios /opt/nagios/etc/conf.d/