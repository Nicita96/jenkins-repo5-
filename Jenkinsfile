pipeline {
    agent {
        docker { 
            label 'docker'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
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
