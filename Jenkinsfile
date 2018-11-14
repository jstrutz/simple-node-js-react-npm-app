pipeline {
  agent {
    docker {
      image 'node:10-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Dependencies') {
      parallel {
        stage('Dependencies') {
          steps {
            sh 'npm ci'
          }
        }
        stage('Other Dep') {
          steps {
            echo 'Hello'
          }
        }
      }
    }
    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }
  }
  environment {
    CI = 'true'
  }
}