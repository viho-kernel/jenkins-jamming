pipeline {
    agent {
        node {
            label 'Agent-1'
        }
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
                echo 'Deploying....'
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