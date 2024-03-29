FROM alpine:latest

# Dependencies
RUN apk update && apk add openjdk11 && apk add maven

# Get the binary
COPY ./target /api
WORKDIR /api

# Expose port 8080
EXPOSE 8080

# Start
CMD java -jar ./tlcdemoApp-1.0.0-SNAPSHOT-runner.jar