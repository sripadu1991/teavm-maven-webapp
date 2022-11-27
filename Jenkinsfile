pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github_cred', url: 'https://github.com/devopsdeepdive/teavm-maven-webapp.git']]])
            }
        }
		 stage('Build') {
            steps {
                sh 'mvn clean'
            }
        }
		 stage('Build') {
            steps {
                sh 'mvn test'
            }
        }
		stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
