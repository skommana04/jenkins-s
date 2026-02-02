pipeline {
    agent {
        node {
            label 'slave1'
        }

    }
    options {
        timeout(time: 10, unit: 'SECONDS')
    }
    environment {
        COURSE = "Jenkins"
    }

    stages {
        stage ('Build') {
            steps {
                sh """
                echo "Building"
                echo $COURSE
                sleep 10
                env
                """
            }
        }
        stage('Test'){
            steps {
                echo "Testing"
            }
        }
        stage('Deploy') {
            steps{
                echo "Depying"
            }
        }

    }
    post {
        always {
            echo "I will always say Hello"
            cleanWs()
        }
        success {
            echo "success"
       }
       failure {
        echo "failure"
       }
    }
}
