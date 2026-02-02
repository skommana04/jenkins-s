pipeline {
    agent {
        node {
            label 'slave1'
        }

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
