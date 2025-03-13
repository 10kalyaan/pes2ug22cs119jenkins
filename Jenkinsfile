pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/10kalyaan/pes2ug22cs119jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'g++ main.cpp -o pes2ug22cs119-1' // Compile the C++ file
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './pes2ug22cs119-1' // Execute compiled file
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
