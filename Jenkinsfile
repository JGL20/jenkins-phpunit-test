pipeline {
	// agent {
	// 	any {
	// 		image 'composer:latest'
	// 	}
	// }
	agent any
	stages {
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
}
