# DevOps-Continuous-Deployment-Pipeline
# CI/CD Pipeline with Jenkins and Tomcat

This project demonstrates a complete CI/CD pipeline for Java web applications using Jenkins for continuous integration and Tomcat for deployment.

## Overview

The CI/CD pipeline automates the following steps:
1. Source code checkout from Git repository
2. Building and compiling the Java code with Maven
3. Running unit tests
4. Packaging the application as a WAR file
5. Deploying to Apache Tomcat
6. Verifying the deployment

## Components

- **Jenkins**: CI/CD server running on port 8080
- **Tomcat**: Application server running on port 9090
- **Maven**: Build tool for Java applications
- **Git**: Source code management

## Project Structure

- **sample-java-app/**: A sample Java web application with Maven project structure
- **jenkins-config/**: Configuration files for Jenkins (Configuration as Code)
- **tomcat-config/**: Configuration files for Tomcat server
- **Jenkinsfile**: Pipeline definition for the CI/CD process
- **setup.sh**: Setup script to configure the environment

## Setup Instructions

### Option 1: Simulated CI/CD Pipeline (Recommended for Replit)

This option provides a simulated CI/CD pipeline experience without requiring Docker:

```bash
# Start the CI/CD pipeline simulator
node start-cicd.js
```

The simulator will be available at: http://localhost:5000

### Option 2: Docker-based Setup

Run the `setup.sh` script to install and configure Docker containers for Jenkins and Tomcat:

```bash
# Make the setup script executable
chmod +x setup.sh

# Run the setup script
./setup.sh

# Start the CI/CD environment manager
node ci-cd-docker/server.js
```

The CI/CD environment manager will be available at: http://localhost:5000

## Using the CI/CD Pipeline

After setting up the environment using either option:

1. **Option 1 (Simulator):**
   - Click the "Start Pipeline" button to simulate the CI/CD process
   - Watch the pipeline stages execute
   - View the simulated logs for each stage

2. **Option 2 (Docker):**
   - Start the Jenkins and Tomcat containers
   - Access Jenkins UI at http://localhost:8080
   - Configure Jenkins with Java and Maven tools
   - Create a pipeline job using the Jenkinsfile
   - Run the pipeline to build and deploy the sample Java application
   - Access the deployed application at http://localhost:9090/java-web-app/

## Sample Application

The sample Java web application includes:
- A simple servlet-based web application
- Maven project configuration
- Basic HTML/JSP files
- Controller classes for request handling

## Jenkins Pipeline

The Jenkinsfile defines a declarative pipeline with stages for:
- Checkout
- Clean & Compile
- Test
- Package
- Deploy to Tomcat
- Verify Deployment

## Tomcat Configuration

Tomcat is configured with:
- Custom port (9090)
- Manager application credentials
- Deployment user for CI/CD integration
