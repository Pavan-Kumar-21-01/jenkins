pipeline {
    agent any
    environment{
        PROJECT = 'expense'
        COMPONENT = 'front-end'
        AUTHOR = 'pavan'
        TEAM = 'devops-team-expense'
    }
    stages{
        stage('one') {
            steps{
                sh "echo Welcome Everyone...!"
            }
        }
        stage('two') {
            steps{
                sh '''
                    echo "Second stage build starts"
                    pwd
                    ls -lrt

                '''
            }
        }
        stage('Env-var-check') {
            steps{
                sh '''
                    echo "We are building a new project named: ${PROJECT} with component as ${COMPONENT}."
                    echo 'And the Team-lead is $AUTHOR leading a team of $TEAM'
                '''
            }
        }
    }
}