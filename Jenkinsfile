pipeline {
	    agent {
        docker {
            image 'composer:latest'
            args '-v /path/to/project:/app'
        }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'composer install'
            }
        }

		stage('Build') {
			steps {
				sh 'composer install'
			      }
			}
		stage('Test') {
		steps {
                sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
           		 }
		}
		}
		post {
			always {
				junit testResults: 'logs/unitreport.xml' 
			}
		}
	
}
