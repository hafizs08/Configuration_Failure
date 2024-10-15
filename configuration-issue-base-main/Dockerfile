# Stage untuk membangun aplikasi
FROM maven:3.9.2-eclipse-temurin-17 AS builder
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Stage untuk menjalankan aplikasi
FROM eclipse-temurin:17-jre-focal AS runner
WORKDIR /app
COPY --from=builder /app/target/example-auth-jwt-custom-0.0.0-E.jar /opt/app.jar

# Port yang dibuka oleh aplikasi
EXPOSE 8080

# Command untuk menjalankan aplikasi
CMD ["java", "-jar", "/opt/app.jar"]
