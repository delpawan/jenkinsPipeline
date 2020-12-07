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

        stage('Test Logs') {
          environment {
            LocalVariable = 'Local Variable.'
          }
          steps {
            writeFile(file: 'logtestfile.txt', text: "This is test log file. Chrome Driver path: ${ChromeDriverPath} and local variable value: ${LocalVariable}")
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to deploy?', id: 'Ok')
            echo 'Deploying in IIS server'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'logtestfile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Chrome'
  }
}