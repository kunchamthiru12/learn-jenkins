pipeline {
    agent {
        node{
            label 'AGENT-1'
        }
    }
    environment {
        GREETING = 'Hello Jenkins'
    }
    options{
        timeout(time:1,unit:'SECONDS')
    }
//build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh"""
                echo "here I wrote shell script"
                echo "$GREETING "
                """
            }
        }
    }

    //post build
    post {
        always{
            echo 'I willalways say Hello again!'
        }
        failure{
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo ' i say Hello pipeline is successs'
        }
    }
}