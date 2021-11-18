pipeline {
  agent { label 'master' }

  environment {
      DOC = credentials('dockerhub-aguscuk')
  }
  
  stages {
          
    
            
    stage('Deploy') {
      steps {
        script {
          sh '''!/usr/bin/env bash
            echo ${params.USER}
          '''
        }
      }
    }
  }
}
