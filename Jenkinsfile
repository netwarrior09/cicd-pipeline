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
        sh 'sudo docker build -t kkm-epam-image .'
      }
    }

    stage('docker-push') {
      environment {
        DOCKER_USER = 'kassiyenov'
        DOCKER_PASS = 'u2YFvd2xr4kx*'
      }
      steps {
        sh '''sudo docker login -u $DOCKER_USER -p $DOCKER_PASS
sudo docker push kassiyenov/epam/kkm-epam-image:latest'''
      }
    }

  }
}