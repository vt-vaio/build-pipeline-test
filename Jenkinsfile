/* Requires the Docker Pipeline plugin */
pipeline {
    //agent { docker { image 'python:3.11.4-alpine3.18' } }
    agent {
        docker { 
            image 'stm32-test-image:latest' 
            args '-v $HOME:/srv/jekyll'
        }
    }
    stages {
        // stage('test') {
        //     steps {
        //         dir(path: '/'){
        //             sh 'ls -al'
        //         }
        //     }
        // }
        stage('build') {
            steps {
                // sh 'git clone https://github.com/vt-vaio/build-pipeline-test.git'
                sh 'pwd'
                sh 'ls -al'
                //sh 'curl -LO https://cdn.rowleydownload.co.uk/arm/releases/arm_crossworks_4_10_4_linux_arm64.tar.gz'
                //sh 'tar -xf arm_crossworks_4_10_4_linux_arm64.tar.gz'
                //sh './arm_crossworks_4_10_linux_arm64/install_crossworks --accept-license --copy-files-to crossworks'
                sh 'cd /root'
                sh 'ls -al'
                sh './crossworks/bin/crossbuild -config "THUMB Debug" ./build-pipeline-test/STM32TestProject.hzp'
            }
        }
    }
}