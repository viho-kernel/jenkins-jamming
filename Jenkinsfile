pipeline {
    agent {
        node {
            label 'Agent-1'
        }
    }
    environment {
        GREETING = "Hello Jenkins"
    }
    options {
        timeout(time:2, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
         stage('checking params') {
            steps {
               echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
        stage('Deploy') {
            steps {
              sh """
              echo "Deployed.."
              echo "$GREETING"
              sleep 10
              echo "Configured Webhooks"
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