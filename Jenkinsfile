pipeline {
  agent any
  stages {
    stage('Download') {
      steps {
        nodejs('node-latest') {
          sh 'npm install'
          sh 'npm install -g @angular/cli'
        }

      }
    }

    stage('build') {
      agent {
        node {
          label 'slave'
        }

      }
      steps {
        nodejs('node-latest') {
          sh 'ng build'
        }

      }
    }

  }
}