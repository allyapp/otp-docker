FROM openjdk:8-jre-alpine
MAINTAINER Marcel Radischat <marcel@door2door.io>

RUN apk update
RUN apk add wget ca-certificates bash
RUN update-ca-certificates

#OTP
RUN mkdir -p /opentripplanner/graphs
WORKDIR /opentripplanner
RUN wget -O otp-1.3.0-SNAPSHOT.jar https://s3.eu-central-1.amazonaws.com/d2d-otp/otp-1.3.0-SNAPSHOT.jar

ADD logback.xml /opentripplanner/logback.xml
ADD run.sh /run.sh
RUN chmod +x /run.sh
EXPOSE 8080

ENTRYPOINT ["/run.sh"]