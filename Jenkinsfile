def ex(param){
    error('BAD PARAM: ' + param)
}

pipeline {
    agent any
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'develop', description: 'Select branch to deploy')
    }

    stages {
        stage('Validation') {
            steps {
                script {
                    if ("${params.BRANCH_NAME}" == "release") {ex("BRANCH_NAME can not be release")}
                    if ("${params.BRANCH_NAME}" == "") {ex("BRANCH_NAME can not be empty")}
                }
            }
        }
        stage('Echo') {
            steps {
                echo 'Test git pull'
                sh 'ls -al'
                echo 'Install JDK 11'
                sh 'sudo apt-get install openjdk-11-jdk'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                echo 'Deploy successful!'
            }
        }
    }
}