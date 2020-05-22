pipeline {
	agent any
    environment {
        CI = 'true'
    }
    stages {
		stage('Validacion') {
            steps {
                powershell 'cd simple'
				powershell 'mvn validate'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}