pipeline {
    agent any
    options{
        timeout(time: 15, unit: 'MINUTES')
    }
    environment{
        ACC_ID = '945360925177'
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
        stage('docker'){
            steps{
                script{
                     withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws_cred', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                        sh """
                        aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin ${ACC_ID}.dkr.ecr.us-east-1.amazonaws.com
                
                        """
                    }
                }
                
            }
        }
    }
}