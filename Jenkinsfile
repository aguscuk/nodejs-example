pipeline {
  agent any
  stages {
          
    stage('Build Image') {
      steps {
        script {
          if (env.GIT_BRANCH == 'origin/development') {
            sh '''
             echo "Build image process"
             sh "docker build -t aguscuk/nodejs-example:${env.BUILD_NUMBER} ."
             '''
          }
        }
      }
    }

    stage('Push Image') {
      steps {
        sh '''
         echo "Push image process"
         sh "docker push ${REGISTRY_DEV}:${env.BUILD_NUMBER}"
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
