pipeline {
    agent any
    stages {
        // stage('Clone repository') {
        //     steps {
        //         checkout([$class: 'GitSCM', 
        //         branches: [[name: '*/main']],
        //         userRemoteConfigs: [[url: 'https://github.com/ankitam389/PES2UG21CS076_Jenkins.git']]])

        //     }

        // }

        stage('Build') {
            steps {
                build 'PES2UG21CS076-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }

    }
    post{
        failure{
        error 'Pipeline failed'
        }
    }
}
