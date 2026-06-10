pipeline {
    agent any
    environment{
        PROJECT = 'expense'
        COMPONENT = 'front-end'
        AUTHOR = 'pavan'
        TEAM = 'devops-team-expense'
    }
    options{
        timeout(time: 15, unit: 'MINUTES')
    }
    parameters{
        string(name: 'PERSON',defaultValue: 'Mr.G.Pavan Kumar', description: 'Author of this Jenkinsfile')
        text(name: 'Subject Details',defaultValue: 'Learning Devops and AWS')
        booleanParam(name: 'TOGGLE', defaultValue: 'true')
        choice(name: 'CHOICE', choices: ['Dev','QA','Prod','Pre-Prod'])
        password(name: 'PASSWORD',defaultValue: 'secret',description: 'Enter password')

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
                    echo "And the Team-lead is $AUTHOR leading a team of $TEAM"
                '''
            }
        }
        stage('param-check') {
            steps{
                sh '''
                    echo "checking parameters passed: ${param.PERSON} and ${param.Subject Details}"
                    echo "toggle:${param.TOGGLE}"
                    echo "choice: ${param.CHOICE}"
                    echo "password:${param.PASSWORD}"
                '''
            }
        }
    }
}