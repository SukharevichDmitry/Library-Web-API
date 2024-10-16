FROM openjdk:23-jdk-slim

WORKDIR /app

COPY LibraryService-1.0-SNAPSHOT.jar libraryservice.jar

EXPOSE 8082

ENTRYPOINT ["java", "-jar", "/app/libraryservice.jar"]


