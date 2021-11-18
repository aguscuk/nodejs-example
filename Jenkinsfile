pipeline {
  agent { label 'master' }

  environment {
      DOC = credentials('dockerhub-aguscuk')
  }
  
  stages {
    stage('testing') {
      steps {
        script {
          sh '''
          echo hostname
          '''
        }
      }
    } 
    
    
    
    
  }
}  
  
