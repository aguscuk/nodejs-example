  environment {
    REGISTRY_DEV = 'aguscuk/nodejs-example'
    DEPLOYMENT_DEV = 'nodejs-example'
  }

pipeline {
  agent any
  stages {
     
    stage('Git Clone') {
      agent {
        label 'master'
      }      
      steps {
        sh '''
        echo "Git clone process"
        '''
      }
    }
     
    stage('Build Image') {
      steps {
        sh '''
         echo "Build image process"
         sh "docker build -t ${REGISTRY_DEV}:${env.BUILD_NUMBER} ."
         '''
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
