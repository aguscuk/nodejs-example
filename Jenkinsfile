pipeline {
  agent any
  stages {
    agent {
      label 'master'
    }        
    stage('Git Clone') {
      steps {
        sh '''
        echo "Git clone process"
        '''
      }
    }
     
    stage('Build Image') {
      steps {
        sh '''
         echo "build process"
         '''
      }
    }

    stage('Push Image') {
      steps {
        sh '''
         echo "Push process"
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
