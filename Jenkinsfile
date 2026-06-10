pipeline {
    agent any
    options{
        timeout(time: 15, unit: 'MINUTES')
    }
    stages{
        stage("Read Versions"){
            steps{
                script {
                    def packageJson = readJSON file: 'package.json'
                    appVersion = packageJson.version
                    echo "The current version is: ${appVersion}"
                    env.APP_VERSION = appVersion
                }
            }
        }
        stage("git checkout"){
            steps{
                echo "Hello git"
            }
        }
    }
}