# setup alpine container to be a Jenkins agent for Nginx

FROM python:alpine3.17

# install add reqired packages
RUN apk update
RUN apk upgrade
RUN apk add openjdk11
RUN apk add git
RUN apk add openssh
RUN pip install Flask
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

# add jenkins usser
RUN adduser -h /usr/share/jenkins jenkins; echo 'jenkins:jenkins' | chpasswd

ENTRYPOINT [ "./entrypoint.sh" ]
