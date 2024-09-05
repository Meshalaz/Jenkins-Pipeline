pipeline {
    agent any
    stages {
        stage('Pull Code') {
            steps {
                echo 'Pulling code from GitHub repository'
               
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project using Maven'
                bat 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration tests using JUnit and Selenium'
                bat 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis using SonarQube'
                bat 'mvn sonar:sonar'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency Check'
                bat 'dependency-check --project "MyProject" --scan ./'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to AWS EC2 Staging'
                bat 'scp target/my-app.jar user@staging-ec2-instance:/path/to/app/'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on Staging using Selenium or Postman'
                bat 'selenium-runner --tests staging-integration-tests'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to AWS EC2 Production'
                bat 'scp target/my-app.jar user@production-ec2-instance:/path/to/app/'
            }
        }
    }
}
