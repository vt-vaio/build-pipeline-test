/* Requires the Docker Pipeline plugin */
pipeline {
    //agent { docker { image 'python:3.11.4-alpine3.18' } }
    agent {
        docker { image 'stm32-test-image:latest' }
    }
    stages {
        stage('build') {
            steps {
                sh 'echo "Clone repo https://github.com/vt-vaio/build-pipeline-test.git"'
                sh 'git clone https://github.com/vt-vaio/build-pipeline-test.git'
            }
        }
    }
}
