pipeline {
    agent any

    environment{
        DIRECTORY_PATH = 'C:\\Users\\mouch\\AppData\\Local\\Jenkins\\.jenkins\\workspace\\My_first_job'
        TESTING_ENVIRONMENT = 'Staging'
        PRODUCTION_ENVIRONMENT = 'Meshal'
    }

    stages{
        stage('BUILD'){
            steps{
                echo "fetch the source code from $DIRECTORY_PATH"
                echo "compile the code and generate any necessary artifact"
            }
        }
        
        stage('TEST'){
            steps{
                echo "unit tests"
                echo 'integration tests'
            }
        }

        stage('CODE QUALITY CHECK'){
            steps{
                echo "check the quality of the code"
            }
        }

        stage('DEPLOY'){
            steps{
                echo "deploy the application to a $TESTING_ENVIRONMENT"
            }
        }

        stage('APPROVAL'){
            steps{
                echo "pausing for manual approval"
                sleep (time: 10, unit : 'SECONDS') 
            }
        }
        
        stage('DEPLOY TO PRODUCTION'){
            steps{
                echo "$PRODUCTION_ENVIRONMENT"
            }
        }
    }
}