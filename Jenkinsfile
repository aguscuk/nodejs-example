pipeline {
  agent { label 'master' }
  
  stages {
          
    stage('Build Image') {
      steps {
        script {
          if (env.GIT_BRANCH == 'origin/development') {
            sh '''
             echo "Build image process"
             sh "docker build -t aguscuk/nodejs-example:latest ."
             '''
          }
        }
      }
    }

    stage('Push Image') {
      steps {
        sh '''
         echo "Push image process"
         sh "docker push aguscuk/nodejs-exmaple:latest"
         '''
      }
    }   
    
            
    stage('Deploy') {
      steps {
        sh '''
        echo "Deploy process"
        '''
      }
    }
  }
}
