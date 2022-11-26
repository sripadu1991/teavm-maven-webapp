pipeline {
    agent any 
	parameters {
  string description: 'This is my branch', name: 'BRANCH_NAME'
}
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
		 stage('package') { 
            steps {
               sh 'mvn package' 
            }
        }
    }
}
