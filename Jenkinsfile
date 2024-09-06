pipeline {
    agent any

    stages {
        stage('BUILD') {
            steps {
                echo "Building the code using Maven"
                echo "Maven building tool"
            }
        }

        stage('UNIT AND INTEGRATION TESTS') {
            steps {
                echo "Running unit and integration test using JUnit"
                echo 'JUnit testing tool'
            }
               post {
        success {
            emailext body: "Build ${currentBuild.fullDisplayName} succeeded",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - Successful",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
        failure {
            emailext body: "Build ${currentBuild.fullDisplayName} failed",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - Failed",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
        unstable {
            emailext body: "Build ${currentBuild.fullDisplayName} is unstable",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - Unstable",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
        always {
            emailext body: "Build ${currentBuild.fullDisplayName} has finished with status ${currentBuild.currentResult}",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
    }
            }
        }

        stage('CODE ANALYSIS') {
            steps {
                echo "Running code analysis using GitHub"
                echo "GitHub code analysis tool"
            }
        }

        stage('SECURITY SCAN') {
            steps {
                echo "Performing a security scan on the code using an OWASP tool"
                echo "OWASP security scanning tool"
            }
                   post {
        success {
            emailext body: "Build ${currentBuild.fullDisplayName} succeeded",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - Successful",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
        failure {
            emailext body: "Build ${currentBuild.fullDisplayName} failed",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - Failed",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
        unstable {
            emailext body: "Build ${currentBuild.fullDisplayName} is unstable",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - Unstable",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
        always {
            emailext body: "Build ${currentBuild.fullDisplayName} has finished with status ${currentBuild.currentResult}",
                     subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                     to: 'iimouchy.7@gmail.com',
                     attachLog: true
        }
    }
        }

        stage('DEPLOY TO STAGING') {
            steps {
                echo "Deploy the application to AWS EC2 server"
                echo "AWS EC2 for staging deployment"
            }
        }

        stage('INTEGRATION TESTS ON STAGING') {
            steps {
                echo "Running integration tests on the staging environment"
            }
        }

        stage('DEPLOY TO PRODUCTION') {
            steps {
                echo "Deploying the application to an AWS EC2 server"
                echo "AWS EC2 for production deployment"
            }
        }
    }

