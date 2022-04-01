pipeline {
    agent { label 'docker' }
    
    stages {
        stage('Initialize'){
            steps {
                script {
                    def dockerHome = tool 'myDocker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                    }
                }
            }
        stage('Test') {
            steps {
                sh 'usermod -a -G docker $USER'
                sh 'docker --version'
                sh 'docker ps'
            }
        }
    }
    post {
        always {
        cleanWs()
        }
    }
}
