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

        stage('Kubernetes Version') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig', variable: 'KUBECONFIG_FILE')]) {
                    sh '''
                    sshpass -p 'pass' ssh -o StrictHostKeyChecking=no root@192.168.0.121 -C "
                    export KUBECONFIG=/etc/kubernetes/admin.conf &&
                    kubectl version"
                    '''
                }
            }
        }
    }
}
