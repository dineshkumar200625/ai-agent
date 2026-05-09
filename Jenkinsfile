pipeline {
    agent any
    stages {
        stage('Build & Push Agent') {
            steps {
                sh 'docker build -t dinesh200625/sre-agent:latest .'
                sh 'docker push dinesh200625/sre-agent:latest'
            }
        }
        stage('Deploy Agent') {
            steps {
                sh '/var/jenkins_home/bin/kubectl apply -f deployment.yaml'
            }
        }
    }
}
