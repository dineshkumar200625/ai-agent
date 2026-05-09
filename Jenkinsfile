pipeline {
    agent any
    stages {
        stage('Build & Push Agent') {
    steps {
        
        sh "/usr/bin/docker build -t dinesh200625/sre-agent:latest ."
        sh "echo $DOCKER_CREDS_PSW | /usr/bin/docker login -u $DOCKER_CREDS_USR --password-stdin"
        sh "/usr/bin/docker push dinesh200625/sre-agent:latest"
    }
}
        stage('Deploy Agent') {
            steps {
                sh '/var/jenkins_home/bin/kubectl apply -f deployment.yaml'
            }
        }
    }
}
