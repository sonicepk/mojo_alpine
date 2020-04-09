# mojo_alpine
# Basic mojo alpine container and push to dockerhub

This docker image can be used with other Docker files 
FROM sonicepk/mojo_alpine:latest

RUN mkdir /opt/my-app
WORKDIR /opt/my-app
ADD my_app . 

RUN apk update && \
  apk add sipcalc ipcalc

EXPOSE 80
CMD ["hypnotoad", "-f", "script/my_ip"]
