FROM maven:3.9-eclipse-temurin-17 AS builder
WORKDIR /app
COPY . .
RUN mvn clean install -DskipTests

FROM eclipse-temurin:17-jre
RUN mkdir -p app/app_jar
COPY --from=builder /app/target/*.jar /app/app_jar
EXPOSE 8080
ENTRYPOINT [ "java","-jar","/app/app_jar/EcommerceApp.jar" ]