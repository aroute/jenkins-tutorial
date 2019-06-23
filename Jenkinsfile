pipeline {
  agent {
    docker {
      image 'docker.io/maven:3.3.3'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'mvn --version'
      }
    }
  }
}
