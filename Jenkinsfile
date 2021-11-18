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
