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
				 script {
				//sh 'composer install'
		sh 'docker run --rm -v $PWD:/app -w /app composer:latest composer install'
                }
				
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
            }
		}
	}
}
