pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'script ./script/build.sh'
      }
    }

    stage('test') {
      steps {
        sh 'script ./scripts/test.sh'
      }
    }

  }
}