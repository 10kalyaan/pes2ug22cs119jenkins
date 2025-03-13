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
               
                sh 'g++ main.cpp -o output'

            } 
        }
 
         stage('Test') { 
             steps { 
                 script { 
                     sh './pes2ug22cs119-1' 
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
