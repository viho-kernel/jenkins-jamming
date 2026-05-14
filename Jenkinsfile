pipeline {
    agent any 
    environment {
        APP_NAME = "Roboshop"
        DEPLOY_ENV = "stagging"
    }
    stages {
        stage('Build') {
            steps {
              script {
                sh """
                  echo "Building ${APP_NAME}"
                """
              }
            }
        }
    }
//post build
    post { 
        always { 
            echo 'I will always run!'
        }
        success {
            echo "The ${DEPLOY_ENV} environment pipeline is succeeded!"
        }
        failure {
            echo 'The pipeline failed :('
        }
    }
}