pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
    
  }
  stages {
    stage('build') {
      steps {
        sh 'npm install'
      }
    }
    stage('test') {
      environment {
        Cl = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
  }
}