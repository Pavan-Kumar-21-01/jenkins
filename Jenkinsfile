pipeline{
    agent any
    stages{
        stage("parallel-stages"){
            parallel {
                stage('Git pull'){
                    steps{
                        echo "git pulled stage-1"
                    }
                }
                stage('Build') {
                    steps{
                        echo "git build"
                    }
                }
            }

        }
    }
}