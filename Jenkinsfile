pipeline {
    agent any 
    
    stages {
        agent {
            docker { 
                image 'node:16.13.1-alpine'
                label 'docker'
            }
        }
        stage('Initialize'){
            def dockerHome = tool 'myDocker'
            env.PATH = "${dockerHome}/bin:${env.PATH}"
        }     
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
    post {
      always {
        cleanWs()
        }
    }
}
