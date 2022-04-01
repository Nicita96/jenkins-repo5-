pipeline {
    agent any
    
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
                sh 'whoami'
                sh 'hostname'
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
