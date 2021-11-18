pipeline {
  agent { label 'master' }

  environment {
      DOC = credentials('dockerhub-aguscuk')
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
            docker build -t aguscuk/nodejs-example:latest .
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
              docker push aguscuk/nodejs-example:latest
            '''
          }
        }
      }
    }   
    
            
    stage('Deploy') {
      steps {
        script {
          sh """
          echo "Deploy process"
          ssh ${params.USER}@${params.SERVER} -p ${params.PORT} 'docker rm -f my-node'
          ssh ${params.USER}@${params.SERVER} -p ${params.PORT} 'docker run -d --name my-node -p8989:8080 aguscuk/nodejs-example:latest'
          """
        }
        
      }
    }
  }
}
