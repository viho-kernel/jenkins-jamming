pipeline {
    agent any 
    environment {
        APP_NAME = "Roboshop"
        DEPLOY_ENV = "stagging"
    }
    parameters {
         string(name: 'DEPLOY_ENV',  defaultValue: 'staging, production, testing', description: 'Target environment')
        choice(name: 'VERSION', choices: ['v1', 'v2', 'v3'], description: 'Select version')
        booleanParam(name: 'DEBUG_MODE', defaultValue: false, description: 'Enable debug logs?')
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
            echo "The ${params.DEPLOY_ENV} ${DEPLOY_ENV} environment pipeline is succeeded!"
        }
        failure {
            echo 'The pipeline failed ):-:('
        }
    }
}