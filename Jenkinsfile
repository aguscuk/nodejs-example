pipeline {
  agent { label 'master' }

  environment {
      DOC = credentials('dockerhub-aguscuk')
  }
  
  stages {
    stage('testing') {
      steps {
          sh '''#!/bin/bash -xe
          echo $params.USER
          '''
      }
    } 
    
    
    
    
  }
}  
  
