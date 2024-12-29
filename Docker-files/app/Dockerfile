# Stage 1: Build the .war file using Maven
FROM maven:3.8.6-openjdk-11-slim AS build

# Set the working directory for Maven
WORKDIR /app

# Copy your pom.xml and source code to the Docker image
COPY pom.xml /app/pom.xml
COPY src /app/src

# Run Maven to build the project and package the WAR file
RUN mvn clean package -DskipTests

# Stage 2: Set up Tomcat and deploy the WAR file
FROM tomcat:9.0

# Copy the WAR file generated in the build stage into Tomcat's webapps directory
COPY --from=build /app/target/my-webapp.war /usr/local/tomcat/webapps/ROOT.war

# Expose the port Tomcat is running on (default is 8080)
EXPOSE 8080

# Start Tomcat when the container starts
CMD ["catalina.sh", "run"]
