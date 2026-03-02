FROM eclipse-temurin
WORKDIR /app
COPY . /app/
RUN mvn clean install
COPY /app/target/*.jar /app/app_jar
EXPOSE 8080
ENTRYPOINT [ "java","jar","/app/app_jar/EcommerceApp.jar" ]