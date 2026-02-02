pipeline {
    agent {
        node {
            label 'slave1'
        }

    }
    stages {
        stage ('Build') {
            steps {
            echo "Building"
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
