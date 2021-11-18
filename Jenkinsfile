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
        echo params.USER
        echo params.SERVER
        echo params.PORT
        
        //ssh params.USER@params.SERVER -p params.PORT "hostname"
        '''
      }
    }
  }
}
