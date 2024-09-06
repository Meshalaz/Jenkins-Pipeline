pipeline {
    agent any

    stages{
        stage('BUILD'){
            steps{
                echo "Building the code using Maven"
                echo "Maven building tool"
            }
        }
        
        stage('UNIT AND INTEGRATION TESTS'){
            steps{
                echo "Running unit and integration test using JUnit"
                echo 'JUnit testing tool'
            }
            
        post {
            always {
                emailext(
                    to: 'iimouchy.7@gmail.com',
                    subject: "Jenkins Build: ${currentBuild.fullDisplayName} - Security Scan",
                    body: """
                    Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL}) complete.
                    Stage: Unit and Integration Tests
                    Status: ${currentBuild.currentResult}. 
                    Logs: ${env.BUILD_URL}/console
                    """,
                    attachLog: true
                    )
            }
        }
    }

        stage('CODE ANALYSIS'){
            steps{
                echo "Running code analysis using GitHub"
                echo "GitHub code analysis tool"
            }
        }
          stage('SECURITY SCAN'){
            steps{
                echo "Performing a security scan on the code using a OWASP tool"
                echo "OWASP security scanning tool"
         }
        post {
            always {
                emailext(
                    to: 'iimouchy.7@gmail.com',
                    subject: "Jenkins Build: ${currentBuild.fullDisplayName} - Security Scan",
                    body: """
                    Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL}) complete.
                    Stage: Unit and Integration Tests
                    Status: ${currentBuild.currentResult}. 
                    Logs: ${env.BUILD_URL}/console
                    """,
                    attachLog: true
                    )
            }
        }
          }

        stage('DEPLOY TO STAGING'){
            steps{
                echo "deploy the application to AWS EC2 server"
                echo "AWS EC2 for staging deployment"
            }
        }

        stage('INTEGRATION TESTS ON STAGING'){
            steps{
                echo "Running integration tests on the staging environment"
            }
        }
        
        stage('DEPLOY TO PRODUCTION'){
            steps{
                echo "deploying the application to a AWS EC2 server"
                echo "AWS EC2 for production deployment"

            }
        }
    }
}
