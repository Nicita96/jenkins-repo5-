pipeline {
    agent { label 'docker' }
    
    stages {
        stage('Initialize'){
            steps {
                script {
                    def dockerHome = tool 'myDocker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                    sh 'chmod 666 /var/run/docker.sock'
                    }
                }
            }
        stage('Test') {
            steps {
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
