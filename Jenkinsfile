pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Testing email notifications'
            }
        }
    }

    post {
        always {
            emailext(
                to: 'iimouchy7@gmail.com',
                subject: "Test Email Notification from Jenkins",
                body: """
                This is a test email to verify Jenkins email notifications.
                """,
                attachLog: true
            )
        }
    }
}
