FROM maven:3.9-eclipse-temurin-17 as build

COPY pom.xml .
COPY src src

RUN mvn package

FROM eclipse-temurin:25-jre-alpine as base

COPY --from=build /target/*.jar /app.jar

ENTRYPOINT ["java", "-jar", "/app.jar"]