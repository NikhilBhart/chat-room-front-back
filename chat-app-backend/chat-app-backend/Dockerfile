FROM maven:3.9.4-openjdk:21-jdk-slim AS builder


WORKDIR /app

# Copy source code
COPY . .

# Build the project
RUN mvn clean package -DskipTests

FROM amd64/openjdk:21-jdk-slim

COPY target/chat-app-backend-0.0.1-SNAPSHOT.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
