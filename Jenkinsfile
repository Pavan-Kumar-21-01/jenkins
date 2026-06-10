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
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                script{
                    sh """
                    echo "project: $PROJECT"
                    
                    echo "text: ${params.BIOGRAPHY}"
                    echo "toggle:${params.TOGGLE}"
                    echo "choice: ${params.CHOICE}"
                    echo "password:${params.PASSWORD}"
                """
                }
            }
        }
        stage('deploy') {
            steps{
                script{
                    sh """
                    echo "This is deploy: ${PROJECT}"
                    """
                }
            }
        }
    }
}