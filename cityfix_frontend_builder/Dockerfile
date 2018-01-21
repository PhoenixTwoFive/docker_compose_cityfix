#Aktuellstes Alpine-Linux Basisimage, deutlich leichtgewichtiger und sicherer als Ubuntu, da speziell für Container gedacht.
FROM alpine:latest

# NodeJS und NPM installieren
RUN apk update --no-cache
RUN apk fix --no-cache
RUN apk add --no-cache wget nano alpine-sdk
RUN apk add --no-cache python2
RUN apk add --no-cache nodejs
RUN apk add --no-cache nodejs-npm

# angular
RUN npm install -g @angular/cli --unsafe


# Ports zum Host öffnen (für "ng serve" und "ng test")
EXPOSE 4200
EXPOSE 9876

# OpenSSH-Client (für Deployment)
RUN apk add --no-cache openssh-client

#Build-Script
COPY ./build.sh /root/workspace/build.sh

WORKDIR /root/workspace

CMD sh