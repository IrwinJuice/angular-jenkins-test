pipeline {
    agent any

    tools {
      nodejs "Node"
      git "Default"
    }

    stages {
        stage('Build') {
            steps {
                powershell 'npm install'
                powershell 'ng build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
