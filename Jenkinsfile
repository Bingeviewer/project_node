pipeline {
    agent any
    tools {
        jdk "jdk8"
    }

    stages {
        stage("sonarquality check with maven") {
            agent {
                docker {
                    image "maven"
                }
            }
            steps {
                withSonarQubeEnv(credentialsId: 'jenkins') {
                    sh "mvn clean package sonar:sonar"
                }
            }
        }

    }
}