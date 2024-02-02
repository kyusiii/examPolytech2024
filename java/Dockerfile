FROM maven:3.9-eclipse-temurin-8 AS builder

WORKDIR /application

COPY . .

RUN mvn clean package -DskipTests



FROM eclipse-temurin:8-jre

WORKDIR /application

COPY --from=builder /application/target/*.jar back.jar

LABEL maintainer="martin"

CMD ["java", "-jar", "back.jar"]