/* Requires the Docker Pipeline plugin */
pipeline {
    //agent { docker { image 'python:3.11.4-alpine3.18' } }
    agent {
        docker { 
            image 'stm32-test-image:latest' 
        }
    }
    stages {
        stage('build') {
            steps {
                //sh 'git clone https://github.com/vt-vaio/build-pipeline-test.git'
                sh 'pwd'
                sh 'ls -al'
                './crossworks/bin/crossbuild -config "THUMB Debug" ./STM32TestProject.hzp'
                //sh './crossworks/bin/crossbuild'
            }
        }
    }
}