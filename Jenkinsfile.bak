pipeline {
    agent {
        docker {
            image 'node:14-alpine' 
            args '-p 3003:3003' 
        }
    }
	environment {
        CI = 'true' 
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
		stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}
