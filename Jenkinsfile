pipeline {
    agent any

    stages {
        stage('Checkout from git repo') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/igwej408/buymore.git']])
            }
        }

         stage('build docker image') {
              steps{
                  script{
                     sh 'docker build -t aniediogo/buymore:1 .'
                     
                }
            }
      }
    }
}