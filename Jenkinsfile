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
    post {
        always {
        cleanWs()
        }
    }
}
