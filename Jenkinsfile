pipeline {
    agent any

    stages {
        stage('Git Version') {
            steps {
                sh 'git version'
            }
        }
    
        stage('Maven Version') {
            steps {
                sh 'mvn -v'
            }
        }
        
        stage('Docker Version') {
            steps {
                sh 'docker -v'
            }
        }
    }
}
