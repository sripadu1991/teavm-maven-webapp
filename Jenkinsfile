pipeline {
    agent any 
     stages {
        stage('Checkout') { 
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github_cred', url: 'https://github.com/devopsdeepdive/mavenwebproject2022.git']]]) 
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
