FROM eclipse-temurin:21-jre-alpine
WORKDIR /app
COPY target/api-gateway-0.0.1-SNAPSHOT.jar app.jar
RUN mkdir -p /app/lib && \
    java -Djarmode=tools -jar app.jar extract --layers --launcher --destination /app/extracted || true
EXPOSE 9000
ENTRYPOINT ["java", "-XX:+UseContainerSupport", "-XX:MaxRAMPercentage=75.0", "-jar", "app.jar"]
