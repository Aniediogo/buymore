pipeline {
   agent any

       
   stages{ 
         stage('Cleanup directory'){
            steps{
               script{
                  deleteDir()
               }
            }
         }


       stage('checkout from git repo') {
               steps {
                 checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Aniediogo/buymore.git']])
               }
       }

   
       stage('build docker image') {
              steps{
                  script{
                     sh 'docker build -t buymore:1 .'
                     sh 'docker run -d -p 8000:8000 buymore:1'
                     
                }
            }
       }
   
       stage('scan with Trivy'){
         steps{
           sh 'trivy image buymore:1 > trivy-result.txt'
         }
       }
     
    }
}    