pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
              script {
                sh """
                  echo "Building"
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
            echo 'The pipeline succeeded!'
        }
    }
}