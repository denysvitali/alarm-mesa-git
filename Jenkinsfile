pipeline {
	agent {
		docker {
			image 'base/devel:latest'
	
		}
	}
	options {
    		skipDefaultCheckout(true)
	}
	stages {
		stage('Pull') {
			steps {
				checkout scm
			}
		}
		stage('Prepare'){
			steps {
        sh 'makepkg .'
			}
		}


	}
	post {
		always {
			cleanWs()
		}
	}
}
