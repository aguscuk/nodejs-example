pipeline {
  agent { label 'master' }

  environment {
    DOC = credentials('dockerhub-aguscuk')
    IMG = "aguscuk/nodejs-example"
  }
  
  stages {
          
    stage('Build Image') {
      steps {
        script {
          if (env.GIT_BRANCH == 'origin/development') {
            sh '''
            pwd
            ls -ltrha
            echo "Build image process"
            docker build -t $IMG:$BUILD_NUMBER .
            '''
          }
        }
      }
    }

    stage('Push Image') {
      steps {
        script {
          if (env.GIT_BRANCH == 'origin/development') {
            sh '''
              echo "Push image process"
              docker login docker.io -u $DOC_USR -p $DOC_PSW
              docker push $IMG:$BUILD_NUMBER
            '''
          }
        }
      }
    }   
    
            
    stage('Deploy') {
      steps {
        script {
          if (env.GIT_BRANCH == 'origin/development') {
            sh """
            echo "Deploy process"
            ssh ${params.USER}@${params.SERVER} -p ${params.PORT} 'docker rm -f my-node'
            ssh ${params.USER}@${params.SERVER} -p ${params.PORT} 'docker run -d --name my-node -p8989:8080 ${IMG}:${BUILD_NUMBER}'
            """
          }          
        }
        
      }
    }
    
    stage('Delete Image') {
      steps {
        script {
          if (env.GIT_BRANCH == 'origin/development') {
            sh '''
              echo "Delete image process"
              docker rmi $IMG:$BUILD_NUMBER
            '''
          }
        }
      }
    }       
    
    
  }
}
