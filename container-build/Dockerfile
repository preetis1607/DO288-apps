# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.k8s.description="S2I builder for hosting files with Apache HTTPD server" \
      io.k8s.display-name="Apache HTTPD Server" \
      io.openshift.expose-services="8080:http" \
      io.openshift.tags="builder,httpd" \
      io.openshift.s2i.scripts-url="image://${HOME}/s2i/bin"

EXPOSE 8080

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
                    chmod -R g=u /var/log/httpd /var/run/httpd

USER 1001







