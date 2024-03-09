pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'mvn clean install'
                    echo 'Build Stage Successful'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh 'mvn test'
                    echo 'Test Stage Successful'
                    post {
                        always {
                            junit 'target/surefire-reports/ *. xml'
                        }
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    sh 'mvn deploy'
                    echo 'Deployment Successful'
                }
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
