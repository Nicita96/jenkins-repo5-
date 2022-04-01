pipeline {
    agent { label 'docker'}
    
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
                sh 'systemctl status docker'
                sh 'docker run hello-world'
            }
        }
    }
    post {
        always {
        cleanWs()
        }
    }
}
