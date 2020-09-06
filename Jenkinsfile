pipeline {
    agent any

    triggers {
        pollSCM('*/5 * * * 1-5')
    }
    options {
        skipDefaultCheckout(true)
        // Keep the 10 most recent builds
        buildDiscarder(logRotator(numToKeepStr: '10'))
        timestamps()
    }
    environment {
      //PATH="/var/lib/jenkins/miniconda3/bin:$PATH"
    }

    stages {
        stage ("Code pull"){
            steps{
                echo "Code pull"
                checkout scm
            }
        }
        stage('Build environment') {
            steps{
                echo "Build environment"
            }
        }
        stage('Test environment') {
            steps{
                echo "Test environment"
            }            
        }
    }
    post {
        always {
            echo "Posted"
        }
        failure {
            echo "Send e-mail, when failed"
        }
    }
}