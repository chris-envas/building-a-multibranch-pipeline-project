pipeline {
    agent {
        docker {
            image 'node:14-alpine' 
            args '-p 3000:3000 -p 5000:5000 -p 6000:6000' 
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
