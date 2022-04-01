pipeline {
    agent none 
    
    stages {
        stage('Initialize'){
            agent {
                docker { 
                    image 'node:16.13.1-alpine'
                    label 'docker'
            }
            steps {       
                def dockerHome = tool 'myDocker'
                env.PATH = "${dockerHome}/bin:${env.PATH}"
                }
            }
        }
    }
    post {
        always {
        cleanWs()
        }
    }
}
