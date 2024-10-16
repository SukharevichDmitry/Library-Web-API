FROM openjdk:23-jdk-slim

WORKDIR /app

COPY DTO-1.0-SNAPSHOT.jar dto.jar

EXPOSE 8084

ENTRYPOINT ["java", "-jar", "/app/dto.jar"]


