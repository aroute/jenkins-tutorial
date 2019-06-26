pipeline {
  // Assign to docker slave(s) label, could also be 'any'
  agent {
    label 'dockerserver' 
  }

  stages {
    stage('Docker node test') {
      agent {
        docker {
          // Set both label and image
          label 'dockerserver'
          image 'node:7-alpine'
          args '--name docker-node' // list any args
        }
      }
      steps {
        // Steps run in node:7-alpine docker container on docker slave
        sh 'node --version'
      }
    }

    stage('Docker maven test') {
      agent {
        docker {
          // Set both label and image
          label 'dockerserver'
          image 'maven:3-alpine'
        }
      }
      steps {
        // Steps run in maven:3-alpine docker container on docker slave
        sh 'mvn --version'
      }
    }
  }
} 
