pipeline {
	agent any
    environment {
        CI = 'true'
    }
    stages {
		stage('Validacion') {
            steps {
                powershell 'cd simple'
				powershell 'mvn -f simple validate'
            }
        }
        stage('Build') {
            steps {
                powershell 'mvn -f simple  install'
            }
        }
        stage('Test') {
            steps {
                powershell 'mvn -f simple  test'
            }
        }
    }
}