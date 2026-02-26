FROM maven:3.5-jdk-8-alpine 

WORKDIR /code

COPY * .
COPY settings.xml /usr/share/maven/ref/
RUN mvn package -D skipTests

CMD sh