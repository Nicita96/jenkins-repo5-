pipeline {
    agent { label 'docker' }
    
    stages {
        stage('Initialize'){
            steps {
                script {
                    def dockerHome = tool 'myDocker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                    sh 'newgroup docker'
                    sh 'chmod 666 /var/run/docker.sock'
                    sh 'usermod -aG docker ${USER}'                    
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
