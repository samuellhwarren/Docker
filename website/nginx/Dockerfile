# grab latest nginx
FROM nginx:latest

#get zip into nginx
RUN apt-get update && \
    apt-get install zip -y

#replace nginx website.conf file
RUN rm /etc/nginx/conf.d/*
COPY ./website.conf /etc/nginx/conf.d/website.conf

#move then unzip certs
COPY ./lib_le.zip ./etc_le.zip /tmp/
RUN unzip /tmp/etc_le.zip -d /tmp/
RUN unzip /tmp/lib_le.zip -d /tmp/
RUN cp /tmp/etc/letsencrypt /etc/ -r
RUN cp /tmp/var/lib/letsencrypt /var/lib/ -r