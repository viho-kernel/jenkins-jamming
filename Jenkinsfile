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

    parameters {
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Version of the application to build')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Whether to run tests after build')
    }

    options {
        timeout(time: 1, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    stages {
        stage('Build') {
            steps {
                sh """
                echo 'Building... ${params.VERSION} in ${DEPLOY_ENV} environment for project ${PROJECT_NAME}'
                """
            }
        }
        stage('Test') {
            steps {
                sh """
                echo 'Testing... ${params.RUN_TESTS} in environment ${DEPLOY_ENV} for project ${PROJECT_NAME}'
                """
            }
        }
        stage('Deploy') {
            steps {
                sh """
                echo 'Deploying... in environment ${DEPLOY_ENV} for project ${PROJECT_NAME}.'
                """
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }

        success {
            echo 'Pipeline executed successfully.'
            echo "Deployed version: ${params.VERSION}"
            echo "Feeling happy about the deployment!"
        }

        failure {
            echo 'Pipeline execution failed.'
        }
    }
}