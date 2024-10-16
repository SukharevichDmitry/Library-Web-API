FROM openjdk:23-jdk-slim

WORKDIR /app

COPY BookService-1.0-SNAPSHOT.jar bookService.jar

EXPOSE 8081

ENTRYPOINT ["java", "-jar", "/app/bookservice.jar"]


