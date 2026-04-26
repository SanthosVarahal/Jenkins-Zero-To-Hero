# Use stable, production-safe base image (avoid Alpine issues)
FROM eclipse-temurin:17-jre

# Pick the generated jar dynamically
ARG artifact=target/*.jar

# App directory
WORKDIR /opt/app

# Copy jar into container
COPY ${artifact} app.jar

# Expose Spring Boot default port
EXPOSE 8080

# Run with container-aware JVM settings
ENTRYPOINT ["java","-XX:+UseContainerSupport","-jar","app.jar"]
