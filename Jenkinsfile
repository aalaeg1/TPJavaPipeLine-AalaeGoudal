pipeline {
    agent {
        docker {
            // Image Docker Maven (sera créée à l’étape suivante)
            image 'my-maven-git:latest'
            // Cache Maven pour accélérer les builds
            args '-v $HOME/.m2:/root/.m2'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                sh 'rm -rf project'
                sh 'git clone https://github.com/aalaeg1/TPJavaPipeLine-AalaeGoudal.git project'
            }
        }

        stage('Build') {
            steps {
                dir('project/maven') {
                    sh 'mvn clean test package'
                }
            }
        }
    }
}
