pipeline {
  agent {
    docker {
      image 'node:16-alpine'
      args '-e npm_config_cache=/tmp/.npm'
    }
  }

  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
}
