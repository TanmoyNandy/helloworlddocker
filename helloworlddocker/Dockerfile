### BUILD image
FROM maven:3-jdk-11 as builder
# create app folder for sources
RUN mkdir -p /build/helloworlddocker
WORKDIR /build/helloworlddocker
COPY . /build/helloworlddocker
#Download all required dependencies into one layer
RUN mvn -B dependency:resolve dependency:resolve-plugins
# Build application
RUN mvn package
ENTRYPOINT mvn clean verify