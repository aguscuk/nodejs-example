pipeline {
  agent { label 'master' }

  environment {
      DOC = credentials('dockerhub-aguscuk')
  }
  
  stages {
          
    
            
    stage('Deploy') {
      steps {
        sh '''
        
        echo "Deploy process"
        echo "Hello ${params.USER}"
        
        '''
      }
    }
  }
}
