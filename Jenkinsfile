pipeline { 
     agent any 
  
     stages { 
         stage('Build') { 
             steps { 
                 script { 
                     sh 'g++ -o pes2ug22cs119-1 main.cpp' 
                 } 
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
