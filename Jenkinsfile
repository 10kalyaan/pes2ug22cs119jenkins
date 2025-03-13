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
                build 'pes2ug22cs119-1'
               
                sh 'g++ -o  main.cpp -o output'  // Intentional mistake (should be .cpp)

            } 
        }

        stage('Test') { 
            steps { 
                sh './output'
            } 
        }

        stage('Deploy') { 
            steps { 
                echo 'Deploying...'
            } 
        } 
    }

    post { 
        failure { 
            error 'Pipeline failed'
        } 
    } 
}
