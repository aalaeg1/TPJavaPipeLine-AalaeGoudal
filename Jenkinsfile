pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/aalaeg1/TPJavaPipeLine-AalaeGoudal.git project"
            }
        }

        stage('Build') {
            steps {
                dir('project') {
                    sh 'mvn clean test package'
                }
            }
        }
    }
}
