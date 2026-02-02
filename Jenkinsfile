pipeline {
    agent {
        node {
            label 'slave1'
        }

    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr.Jenkins', description: 'hi jenkins')
        text(name: 'biodata', defaultValue: '', description: 'enter info')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
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
                echo "Hello ${params.PERSON}"
                echo "Hello ${params.biodata}"
                echo "Hello ${params.TOGGLE}"
                echo "Hello ${params.CHOICE}"
                echo "Hello ${params.PASSWORD}"
                """
            }
        }
        stage('Test'){
            steps {
                echo "Testing"
            }
        }
        stage('Deploy') {
            // input {
            //     message "continue?"
            //     ok "yes"
            //     submitter "medha"
            //     parameters {
            //         string(name: 'PERSON', defaultValue: 'Mr.Jenkins', description: 'who should i say')
            //     }
            // }
            when {
                expression { "$params.DEPLOY" == "true" }

            }
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
