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
                sh 'mvn compile'
            }
        }
	stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
	stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
	/* stage('Notify') {
            steps {
		    if {
			    slackSend channel: '#devopsdeepdive_batch3', message: 'Build is successful', teamDomain: 'devopsdeepdivebatch', tokenCredentialId: 'slack_batch12' 
            }
		 else {
			 slackSend channel: '#devopsdeepdive_batch3', message: 'Build is failed', teamDomain: 'devopsdeepdivebatch', tokenCredentialId: 'slack_batch12'
		 }
	 }
        } */
    }
}
