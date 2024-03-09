pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using g++ compiler
                    sh 'g++ -o output_file hello.cpp'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Execute the compiled C++ file and print the output
                    sh './output_file'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Add deployment steps here if needed
            }
        }
    }
    
    post {
        always {
            // Display 'pipeline failed' in case of any errors
            echo 'pipeline failed'
        }
    }
}
