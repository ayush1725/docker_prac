# Pull a base image with JDK tools
FROM openjdk:17-jdk-alpine

# Create a folder where the app code will be stored
WORKDIR /app

# Copy the source code from your host machine to your container
COPY . .

# Compile the application code. The `-d` flag places the compiled .class files in the current directory.
RUN javac -d . src/Main.java

# Run the application. The .class files should be in /app.
CMD ["java", "Main"]

