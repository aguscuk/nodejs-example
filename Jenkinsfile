pipeline {
  agent { label 'master' }

  environment {
      DOC = credentials('dockerhub-aguscuk')
  }
  
  stages {
          
    
            
    stage('Deploy') {
      steps {
        script {
          sh '''#!/bin/bash -xe
            echo ${params.USER}
          '''
        }
      }
    }
  }
}
