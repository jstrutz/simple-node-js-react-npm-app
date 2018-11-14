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
        stage('npm install') {
          steps {
            sh 'npm ci'
          }
        }
      }
    }
    stage('Build') {
      failFast true
      parallel {
        stage('npm run build') {
          steps {
            sh 'npm run build'
          }
        }
        stage('npm run lint') {
          steps {
            sh 'npm run lint'
          }
        }
      }
    }
  }
  environment {
    CI = 'true'
  }
}