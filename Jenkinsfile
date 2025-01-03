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

    stage('docker-push') {
      environment {
        DOCKER_USER = 'kassiyenov'
        DOCKER_PASS = 'u2YFvd2xr4kx*'
      }
      steps {
        sh '''docker login -u $DOCKER_USER -p $DOCKER_PASS
docker tag kkm-epam-image kassiyenov/epam
docker push kassiyenov/epam
'''
      }
    }

  }
}