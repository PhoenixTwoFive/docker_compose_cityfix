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
RUN npm install -g typescript@2.7

# Ports zum Host öffnen (für "ng serve" und "ng test")
EXPOSE 4200
EXPOSE 9876

# OpenSSH-Client (für Deployment)
RUN apk add --no-cache openssh-client
# rsync für deployment
RUN apk add --no-cache rsync

WORKDIR /root/workspace

CMD sh
