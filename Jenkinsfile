pipeline {
    agent {
        node {
            label 'Agent-1'
        }
    }
    environment {
        GREETING = "Hello Jenkins"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
              sh """
              echo "Deployed.."
              """
            }
        }
    }

    post {
        always {
            echo "I am Forever"
        }
        failure {
            echo "this runs when pipeline is failed :( "
        }

        success {
            echo "This build is successfull :)"
        }

    }
}