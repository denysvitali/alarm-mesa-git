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
        sh 'pacman -Sy --noconfirm git wget curl sudo'
        sh 'useradd build'
        sh 'sudo -u build -s'
			}
		}

		stage('Build'){
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
