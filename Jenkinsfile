pipeline {
    agent{
        node {
            label 'Agent-1'
        }
    }

    environment {
        PROJECT_NAME = 'MyApp'
        DEPLOY_ENV = 'Development'
    }

    stages {
        stage('Build') {
            steps {
                sh """
                echo 'Building... in ${DEPLOY_ENV} environment for project ${PROJECT_NAME}'
                """
            }
        }
        stage('Test') {
            steps {
                echo 'Testing... in environment ${DEPLOY_ENV} for project ${PROJECT_NAME}'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying... in environment ${DEPLOY_ENV} for project ${PROJECT_NAME}.'
            }
        }
    }
}