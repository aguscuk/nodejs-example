pipeline {
  agent { label 'master' }

  environment {
      DOC = credentials('dockerhub-aguscuk')
  }
  
  stages {
          
    stage('Deploy') {
      steps {
        script {
          sh '''
          echo "user = $params.USER"
          '''
        }
      }
    }
  }
}
