
FROM maven:3.9-eclipse-temurin-17 AS builder

WORKDIR /build


COPY pom.xml .
RUN mvn dependency:go-offline


COPY . .
RUN mvn clean package -DskipTests



FROM eclipse-temurin:17-jre-alpine

WORKDIR /app


RUN addgroup -S appgroup && adduser -S appuser -G appgroup


COPY --from=builder /build/target/*.jar app.jar


USER appuser

ENTRYPOINT ["java", "-jar", "app.jar"]

EXPOSE 8082
