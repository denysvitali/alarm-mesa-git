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
				sh 'pacman -S makepkg'
        sh 'makepkg'
			}
		}


	}
	post {
		always {
			cleanWs()
		}
	}
}
