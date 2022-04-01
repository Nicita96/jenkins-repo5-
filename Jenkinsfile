pipeline {
    agent {
        label "docker"
    }
    
    stages {
        stage('Build') {
            agent {
                docker {
                    label "docker"
                    image "maven:3.8.4-jdk-11"
                }
            }
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
