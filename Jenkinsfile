def ex(param){
    error('BAD PARAM: ' + param)
}

pipeline {
    agent none
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'develop', description: 'Select branch to deploy')
    }

    stages {
        stage('Back-end') {
            agent {
                docker { image 'maven:3.8.1-adoptopenjdk-11' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:16.13.1-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
