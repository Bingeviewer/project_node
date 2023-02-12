pipeline {
    agent any
    tools {
        jdk "jdk8"
        Docker "docker"
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