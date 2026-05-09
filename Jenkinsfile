pipeline {

    agent any

    stages {

        stage('Build & Push Agent') {

            steps {

                sh '''

                ssh -o StrictHostKeyChecking=no \
                ubuntu@13.48.104.167 "

                cd /home/ubuntu/ai-agent

                git pull

                docker build -t dinesh200625/sre-agent:latest .

                docker push dinesh200625/sre-agent:latest

                "

                '''
            }
        }

        stage('Deploy Agent') {

            steps {

                sh '''

                ssh -o StrictHostKeyChecking=no \
                ubuntu@13.48.104.167 "

                kubectl apply -f /home/ubuntu/ai-agent/agent.yaml

                "

                '''
            }
        }
    }
}
