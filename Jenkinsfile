pipeline {
	any agent
    environment {
        CI = 'true'
    }
    stages {
		stage('Validacion') {
            steps {
                sh 'cd simple'
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