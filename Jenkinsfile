pipeline {
   agent any

       
   stages{ 
         stage('Cleanup directory'){
            steps{
               scripts{
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
                     
                }
            }
       }
   
    }
}    