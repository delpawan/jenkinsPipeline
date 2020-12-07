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
            echo "Fetching Chrome Driver Path ${ChromeDriverPath}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to deploy?', id: 'Ok')
        echo 'Deploying in IIS server'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Chrome'
  }
}