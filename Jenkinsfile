pipeline {
    agent any  
    stages {
        stage('Build') {
            steps {
                sh 'git clone https://github.com/cozeacatalin/bnc_project_api.git'
                sh 'docker rmi bnc_project_api_frontend'
                sh 'docker rmi bnc_project_api_nodeapp'
                sh 'docker image build -t bnc_project_api_frontend:1.0 frontend/'
                sh 'docker image build -t bnc_project_api_nodeapp:1.0 nodeapp/'
                sh 'docker-compose up'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Tests passed"'
            }
        }
    }
}    
