pipeline {
    agent any
    options{
        timeout(time: 15, unit: 'MINUTES')
    }
    stages {
        stage('Read Version') {
            steps {
               script{
                 def packageJson = readJSON file: 'package.json'
                 appVersion = packageJson.version
                 echo "Version is: ${appVersion}"
               }
            }
        }
        stage('build'){
            steps{
                sh 'npm install'
            }
        }
    }
}