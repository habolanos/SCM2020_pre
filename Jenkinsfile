pipeline {
    environment {
        CI = 'true'
    }
    stages {
		stage('Validacion') {
            steps {
                sh 'cd ./simple'
            }
			steps {
                sh 'mvn validate'
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