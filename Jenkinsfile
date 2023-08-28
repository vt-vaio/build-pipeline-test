/* Requires the Docker Pipeline plugin */
pipeline {
    //agent { docker { image 'python:3.11.4-alpine3.18' } }
    agent {
        docker { image 'stm32-test-image:latest' }
    }
    stages {
        stage('build') {
            steps {
                // sh 'git clone https://github.com/vt-vaio/build-pipeline-test.git'
                sh 'curl -LO https://cdn.rowleydownload.co.uk/arm/releases/arm_crossworks_4_10_4_linux_arm64.tar.gz'
                sh 'tar -xf arm_crossworks_4_10_4_linux_arm64.tar.gz'
                sh './arm_crossworks_4_10_linux_arm64/install_crossworks --accept-license --copy-files-to crossworks'
                sh 'ls -al'
                sh './crossworks/bin/crossbuild -config "THUMB Debug" ./build-pipeline-test/STM32TestProject.hzp'
            }
        }
    }
}