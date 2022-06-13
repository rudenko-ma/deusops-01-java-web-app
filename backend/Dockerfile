# syntax=docker/dockerfile:1

FROM maven:3-eclipse-temurin-11-alpine as builder
WORKDIR /build
COPY . .
RUN mvn clean package -DskipTests=true 

FROM bellsoft/liberica-openjdk-alpine:11
WORKDIR /app
COPY --from=builder /build/target/studentsystem-*.jar /app/app.jar
EXPOSE 8080
CMD ["java", "-jar", "/app/app.jar"]
