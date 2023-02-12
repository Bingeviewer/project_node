pipeline {
    agent any
    tools {
        maven "maven"
    }

    stages {
        stage("sonarquality check with maven") {
            agent {
                docker {
                    image "maven"
                }
            }
            steps {
                script {
                    withSonarQubeEnv(credentialsId: 'jenkins') {
                        sh "mvn clean package sonar:sonar"
                    }
                }
            }
        }

    }
}