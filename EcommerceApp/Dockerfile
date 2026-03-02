FROM maven:3.9-eclipse-temurin-17 AS noel
WORKDIR /app
COPY . .
RUN mvn clean install -DskipTests

FROM tomcat:9.0-jdk17-temurin
WORKDIR /usr/local/tomcat/webapps
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=noel /app/target/*.war ./ROOT.war
EXPOSE 8080
CMD [ "catalina.sh", "run" ]