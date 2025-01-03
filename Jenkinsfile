pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'script ./scripts/build.sh'
      }
    }

    stage('test') {
      steps {
        sh 'script ./scripts/test.sh'
      }
    }

    stage('docker-build') {
      environment {
        DOCKER_IMG = 'kassiyenov/my-app:latest'
      }
      steps {
        sh 'docker build -t kkm-epam-image .'
      }
    }

  }
}