FROM maven:3.5-jdk-8-alpine AS maven_build

WORKDIR /code

COPY * .
COPY settings.xml /usr/share/maven/ref/
COPY settings-docker.xml /usr/share/maven/ref/

RUN mvn package -D skipTests  --settings settings.xml

#FROM openjdk:8-jre-alpine AS run
FROM openjdk:19-ea-jdk-alpine3.16 AS run
WORKDIR /target
COPY --from=maven_build /code/target/worker-jar-with-dependencies.jar worker-jar-with-dependencies.jar

CMD  java -jar target/worker-jar-with-dependencies.jar