/* Requires the Docker Pipeline plugin */
pipeline {
    //agent { docker { image 'python:3.11.4-alpine3.18' } }
    agent {
        docker { image 'python:stm32-test-image:latest' }
    }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
