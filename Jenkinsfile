pipeline {
  agent {
    docker {
      image 'node:10-alpine'
      args '-p 3000:3000'
    }
  }
  environment {
    CI = 'true'
  }
  stages {
    stage('Dependencies') {
      steps {
        sh 'npm ci'
      }
    }
    stage('Build') 
      steps {
        sh 'npm run build'
      }
    }
  }
}