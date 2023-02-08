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
      steps {
        nodejs('node-latest') {
          sh 'ng build'
        }

      }
    }

    stage('deploy') {
      steps {
        sh 'rsync -avz -e "ssh" ./dist/moonlight/* root@123.43.54.23:/tmp'
      }
    }

  }
}