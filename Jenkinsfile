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

        stage('Delete Files') {
            steps {
                fileOperations([
                    fileDeleteOperation(excludes: '', includes: '**/app.config.js')
                ])
            }
        }

        stage('Zip bundle') {
            steps {
              script {
                def dist = "${WORKSPACE}/dist/angular-jenkins/browser/"
                def zipFileName = 'angular-jenkins.zip'

                zip(zipFile: zipFileName, archive: true, dir: dist)
//                 fileOperations([
//                     fileZipOperation(folderPath: "${dist}")
//                 ])
//                 archiveArtifacts artifacts: zipFileName, allowEmptyArchive: true
              }
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
