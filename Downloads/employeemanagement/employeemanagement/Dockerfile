# Use Java 17 as base image
FROM eclipse-temurin:17-jdk-alpine

# Set working directory inside container
WORKDIR /app

# Copy the entire project
COPY . .

# Make the Maven wrapper executable
RUN chmod +x mvnw

# Build the application (skip tests for speed)
RUN ./mvnw clean package -DskipTests

# Expose the port the app runs on
EXPOSE 8080

# Run the JAR file
CMD ["java", "-jar", "target/*.jar"]