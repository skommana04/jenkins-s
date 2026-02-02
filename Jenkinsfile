pipeline {
    agent {
        node {
            label 'slave1'
        }

    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr.Jenkins', description: 'hi jenkins')
        text(name: 'biodata', defaultValue: '', description: 'enter info')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['one', 'Two', 'three'], description: 'pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    options {
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
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
                #sleep 20
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
        aborted {
            echo "pipeline is aborted"
        }
        success {
            echo "success"
       }
       failure {
        echo "failure"
       }
    }
}
