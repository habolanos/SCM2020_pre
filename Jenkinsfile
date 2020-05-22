pipeline {
	agent any
    environment {
		VARIABLE_X='Variable Ejemplo SCM Usb cali'
		PROJECT_NAME='SCM_CALI'
		BUILD_NUMBER = "${env.BUILD_NUMBER}"
    }
    stages {
		stage('Inicio') {
			steps {
				echo "Proyecto %PROJECT_NAME%'
			}
		}
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
	post {
		always {
            echo "ALWAYS"
			//echo "Proyecto ${PROJECT_NAME} Construccion # ${BUILD_NUMBER}"
            notifyBuild("${currentBuild.currentResult}")
        }
        aborted {
            echo "BUILD ABORTED"
        }
        success {
            echo "BUILD SUCCESS"
            echo "Seria bueno mantener esta construccion"
        }
        unstable {
            echo "BUILD UNSTABLE"
        }
        failure {
            echo "BUILD FAILURE"
        }
	}
}