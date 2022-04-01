pipeline {
    agent {
        docker {
            label "docker"
        }
    }
    
    stages {
        agent {
            docker {
                label "docker"
                image "maven:3.8.4-jdk-11"
            }
        }
        stage('Build') {
            steps {
              sh "mvn -version"
              sh "mvn clean install"
            }
        }
    }
    post {
      always {
        cleanWs()
        }
    }
}
