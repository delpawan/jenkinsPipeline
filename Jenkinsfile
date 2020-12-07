pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building .net core application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application built'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying in IIS server'
      }
    }

  }
}